# README #

Conditional attributes that can be used to show/hide script variables in Unity editor based on some other variable values.

## EXAMPLE ##

    class test : MonoBehaviour
    {
        public bool basic = false;

        // simple bool check
        [ShowWhen("basic")]
        public float basicMustBeTrue = 0.0f;

        public bool hasCamera = false;

        // bool check with condition and value
        [ShowWhen("hasCamera", ShowWhenAttribute.Condition.Equals, true)]
        public Camera onlyWhenHasCamera = null;

        // object not null check
        [Range(0.0f, 10.0f, "onlyWhenHasCamera")]
        public float cameraHeight = 0;

        // condition: cameraHeight > 5.0f
        [ShowWhen("cameraHeight", ShowWhenAttribute.Condition.Greater, 5.0f)]
        public float cameraHeightGreater = 0.0f;

        public string typeSomething;

        // string not empty
        [ShowWhen("typeSomething")]
        public int prevStringIsNotEmpty = 0;
    }
