# python-OOP-Lec8-11-JUN-25
private, protected
* function can be private too:__my_personal_stuff()
* protected : self._number_of_pixels=0
  * It Can be access only from within this.class and from within its children's class.
    * not from outer classes. For example, from main: c1._number_of_pixels
* @override functions, the child can override the parent's function
* Interface in Python:
  * unlike java, C#, you can create Interface (guide of empty functions).
  * in python, to implement interface: 
    * an abstract Class with **ONLY** abstract functions
    * <u>doesn't have properties</u>
    * starts with 'I' at the beginning of the class name.
      * or include 'able', like drawableRounded
  * for example:
  ```
  class IShape(ABC):
    @abstractmenthod
    def get area(self):
        pass
  class Shape(ABC,IShape):
  ```
  * an abstract class can inherent interface, doesn't have to implement the functions of the interface.
  * a non-abstract class can inherent interface, must implement the functions of the interface.
  * need to document for each function in interface:
    * input, output, errors, what the function does
    * 5 rows in total.
  * every important method in a class should be declared in an abstract form (Interface or Class) 
* if no inherent-> private
  * else ->protected 
* extra ways,when to use interface 
  * as an instance:
    * when you want to force an instance, that implemented the interface
    * better coding practice.
    ```
      def talk_phone(m:IMobilePhone, minutes):
        m.talk()
    ```
    * m1:IMobilePhone=megaPhone # declared that will use only what the IMobilePhone has
      * then you can call the function above: talk_phone(m1,20)
  * declarative: an empty interface with well-explained class name like IBestCode
    * to use with if isinstance(c,IBestCode)- the class belongs to this "sub-category"
  * class without children, will use interface