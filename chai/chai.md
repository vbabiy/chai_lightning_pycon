!SLIDE smbullets incremental transition=toss center

# Chai? #
* Easy to use mocking/stubbing framework
* Robust expectation library
* Robust set of Argument Comparators
* Extensive test suite
* API is patterned after the Mocha mocking library

!SLIDE center transition=toss

![GitHub](agora_logo.jpg)
# Hackathon #

## Created by: Aaron Westendorf And I

!SLIDE command transition=toss

# Lets See the Code #

!SLIDE code small transition=toss

# Creating a Mock #
    mock() # Returns a mock object

!SLIDE code small transition=toss

# Mocking object in module #

    @@@ python
    mock(custom_module, 'some_object')
    custom_module.some_object # Is a mock object now

!SLIDE code small transition=toss

# Stubbing #

    @@@ python
    def test_stub_name(self):
        obj = MyClass()
        expect(obj.name).returns("Vitaly Babiy")
        assert_equals('Vitaly Babiy', obj.name)

!SLIDE code small transition=toss

# Expectation #

    @@@ python
    def test_stub_name(self):
        obj = MyClass()
        expect(obj.name).returns("Vitaly").at_least(5)
        for x in xrange(4):
          assert_equals('Vitaly Babiy', obj.name)

        # Raises error, obj.name was not called 5 times

!SLIDE code small transition=toss

# Mocking Example #

    @@@ python
    def test_mock_get(self):
        # Pass in a mock, is stored as _handle
        obj = CustomObject( mock() )

        # Setting a expectation on do
        expect( obj._handle.do ).args('it').returns('ok')
        assert_equals('ok', obj.do('it'))

        # Raises UnexpectedCall, no expectation was set
        assert_raises( UnexpectedCall,
          obj._handle.do_it_again )


!SLIDE smbullets transition=toss

# Expectation API #

    @@@ python
    args(*args, **kwargs)
    returns(value)
    raises(exception)

    times(int)
    at_least(int)
    at_least_once()
    at_most(int)
    at_most_once()
    once()
    any_order()


!SLIDE bullets commandline code transition=toss

# Where to find it#

* It's up on PyPi

    $ pip install chai

* Fork it on github
* https://github.com/agoragames/chai


!SLIDE bullets transition=toss 

# Future #

* ...

