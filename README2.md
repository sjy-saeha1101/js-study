
<script>

var a = 1;
var obj = {
    a: 1,
    b: '2',
    c: [
        1,2,3
    ],
    d: {},
    e: function(){}
}

obj.c.forEach(() => {});


function test(obj, v){
    // obj = v;
    if(obj && obj.a !== undefined){
        obj.a = v;
    }
    // console.log('@@args:', arguments);
    // console.log('test this:', this.a, this);
}


function User(params){
    console.log('@@@@@this:', this);

    let _age = 999;
    this.getAge = function(){
        return _age;
    }
    this.setAge = function(age){
        _age = age;
    }

    var THIS = this;
    this.obj = {
        m1: function(){
            console.log('m1 this:', THIS._age, this)
        },
        m2: () => {
            console.log('m2 this:', this)
        },
        m3: {
            t: () => {
                console.log('m2 this:', this)
            }
        }
    }
}
User.prototype.getName = function(){
    return this.name;
}
User.prototype.setName = function(name){
    this.name = name;
}

class User2 {
    static m1() {
        console.log('@@ static:', this);
    }

    constructor(args) {
        console.log('@@ user2')
    }

    #name = ''
    getName() {
        return this.#name;
    }
    setName(name) {
        this.#name = name;
    }
}

</script>
