!SLIDE smbullets transition=turnUp

# What is Chai #
* Easy to use mocking/stubbing framework
* Robust expectation library
* Extensive test suite
* API is patterned after the Mocha mocking library

!SLIDE smbullets center transition=turnUp

# Where is Chai from?#

![GitHub](agora_logo.jpg)


* AgoraGames Hackathon project
* Created by: Aaron Westendorf And I

!SLIDE command transition=turnUp

# Lets See the Code #

!SLIDE code smaller transition=turnUp

# Creating a Mock #
    class TestCase(Chai):
        def test(self):
            mock() # Returns a mock object

!SLIDE code smaller transition=turnUp

# Mocking object in module #

    import custom_module

    class TestCase(Chai):
        def test(self):    
          mock(custom_module, 'some_object')
          custom_module.some_object # Is a mock object now


!SLIDE code smaller transition=turnUp

# Mocking Example #
    class CustomObject(object):
        def __init__(self, handle):
            _handle = handle
        def do(self, arg):
            return _handle.do(arg)

    class TestCase(Chai):
        def test_mock_get(self):
            obj = CustomObject( mock() ) # Pass in a mock
            expect( obj._handle.do ).args('it').returns('ok')
            assert_equals('ok', obj.do('it'))
            assert_raises( UnexpectedCall, obj._handle.do_it_again )


!SLIDE code smaller transition=turnUp

# Stubbing #

    class MyClass(object):
      def name(self):
        return "MyName"

    class TestCase(Chai):
      def test_stub_name(self):
        obj = MyClass()
        expect(obj.name).returns("Vitaly Babiy")
        assert_equals('Vitaly Babiy', obj.name)

!SLIDE code smaller transition=turnUp

# Expectation #

    class MyClass(object):
        def name(self):
          return "MyName"

    class TestCase(Chai):
        def test_stub_name(self):
            obj = MyClass()
            expect(obj.name).returns("Vitaly Babiy").at_least(5)
            for x in xrange(4):
              assert_equals('Vitaly Babiy', obj.name)

            # Raises error since obj.name was not called 5 times

!SLIDE smbullets transition=turnUp

# Expectation API #

* args
* returns
* raises

* times(int)
* at_least(int)
* at\_least\_once
* at_most(int)
* at\_most\_once
* once
* any_order


!SLIDE bullets commandline code transition=turnUp

# Where to find it#

* It's up on PyPi

    $ pip install chai

* Fork it on github
* https://github.com/agoragames/chai


!SLIDE bullets transition=turnUp 

# Future #

* ...

