## Sqlalchemy playground

### create database or migrate then open a python shell

    >>> from app import Person, Pet
    >>> Person.query.all()
    [<Person 1>, <Person 2>]
    >>> pet1 = Pet(name="pupu", owner=riyad)
    >>> pet2 = Pet(name="cucu", owner=onni)
    >>> pet3 = Pet(name="zuzu", owner=onni)
    >>> db.session.add(pet1)
    >>> db.session.add(pet2)
    >>> db.session.add(pet3)
    >>> db.session.commit()
    >>> persons = Person.query.all()
    >>> persons
    [<Person 1>, <Person 2>]
    >>> persons[0]
    <Person 1>
    >>> persons[0].pets
    <sqlalchemy.orm.dynamic.AppenderBaseQuery object at 0x10c0dbfd0>
    >>> persons[0].pets.all()
    [<Pet 1>]
    >>> persons[1].pets.all()
    [<Pet 2>, <Pet 3>]
    >>> persons[1].pets.all()[0].name
    'cucu'
    >>> persons[1].pets.all()[1].name
    'zuzu'
    >>> persons[0].pets.all()[0]
    <Pet 1>
    >>> persons[0].pets.all()[0].name
    'pupu'
    >>> pets = Pets.query.all()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    NameError: name 'Pets' is not defined
    >>> pets = Pet.query.all()
    >>> pets
    [<Pet 1>, <Pet 2>, <Pet 3>]
    >>> pets[0].name
    'pupu'
    >>> pets[0].owner
    <Person 1>
    >>> pets[0].owner.name
    'riyad'
    >>> pets[1].owner.name
    'onni'
    >>> pets[2].owner.name
    'onni'
    >>> pets[0].owner_id
    1
    >>> pets[1].owner_id
    2
    >>> pets[2].owner_id
    2


