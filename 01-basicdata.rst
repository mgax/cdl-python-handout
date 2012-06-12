examples

::
    >>> 1 + 1
    2

    >>> 2 * 3
    6

    >>> 2.5 * 3
    7.5

    >>> type(1)
    <type 'int'>

    >>> type(7.5)
    <type 'float'>

    >>> a = 13

    >>> type(a)
    <type 'int'>

    >>> 4.0/3
    1.3333333333333333

    >>> a = 4.0/3

    >>> a
    1.3333333333333333

    >>> type(a)
    <type 'float'>


tipul este asociat valorii, nu variabilei

::
    >>> type("Hello")
    <type 'str'>

    >>> "Hello" + "world!"
    'Helloworld!'

    >>> "Your lucky number is %d" % 13
    'Your lucky number is 13'

    >>> "Your other number is %d" % a
    'Your other number is 1'

    >>> "Your other number is %f" % a
    'Your other number is 1.333333'

    >>> "Your other number is %.2f" % a
    'Your other number is 1.33'

    >>> msg = "Your other number is %.2f" % a

    >>> len(msg)
    25

    >>> msg[0]
    'Y'

    >>> msg[1]
    'o'

    >>> msg[-1]
    '3'

    >>> msg[12:17]
    'umber'


string-urile au metode

::
    >>> msg.lower()
    'your other number is 1.33'

    >>> msg.find("number")
    11

    >>> msg.split(" ")
    ['Your', 'other', 'number', 'is', '1.33']


am primit o listă! putem defini propriile liste

::
    >>> l = ['ana', 'are', 'mere']

    >>> l
    ['ana', 'are', 'mere']

    >>> type(l)
    <type 'list'>

    >>> l[0]
    'ana'

    >>> type(l[0])
    <type 'str'>

    >>> l.pop()
    'mere'

    >>> l.append("cartofi")

    >>> l
    ['ana', 'are', 'cartofi']

    >>> l.extend(["si", 3, "mere"])

    >>> l
    ['ana', 'are', 'cartofi', 'si', 3, 'mere']

listele primesc conținut de orice type

::
    >>> type(l[4])
    <type 'int'>

    >>> ' '.join(l)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: sequence item 4: expected string, int found

type checking la runtime

::
    >>> l.pop(4)
    3

    >>> ' '.join(l)
    'ana are cartofi si mere'

remember, string-urile au metode

::
    >>> ship = {'name': "Enterprise", 'enemies': ['ferengi', 'cardassian']}

    >>> len(ship)
    2

    >>> ship.keys()
    ['name', 'enemies']

    >>> type(ship['name'])
    <type 'str'>

    >>> type(ship['enemies'])
    <type 'list'>

primește orice fel de valori

::
    >>> ship['enemies'].append('borg')

    >>> ship
    {'name': 'Enterprise', 'enemies': ['ferengi', 'cardassian', 'borg']}

    >>> ship[1] = 'Riker'

    >>> ship
    {1: 'Riker', 'name': 'Enterprise', 'enemies': ['ferengi', 'cardassian', 'borg']}

primește integer la chei (în general non-mutable values)

::
    >>> ship[l] = "hello"
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unhashable type: 'list'

    >>> del ship['enemies']

    >>> ship
    {1: 'Riker', 'name': 'Enterprise'}


if/else, for

::
    >>> if 2 < 3:
    ...     print "doi e mai mic decat trei!"

    >>> if False:
    ...     print "WTF?!"
    ... else:
    ...     print "totul e ok"

    >>> for c in range(30):
    ...   if c % 2 == 0:
    ...     print "Numar par:", c

    >>> l = [c**2 for c in range(20)]
    >>> for c in l:
    ...     print 'numarul este', c
