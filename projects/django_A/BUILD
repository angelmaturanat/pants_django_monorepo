python_sources(
    name="src",
    restartable=True,
    dependencies=[
        "projects/django_A:src"
    ]
)

docker_image(
    name="django_A_image",
    dependencies=[
        "projects:manage_local",
    ],
)

pex_binary(
    name="manage_local",
    entry_point="manage.py:main",
    dependencies=[
        ":src",
    ],
    layout='loose', # layout loose is essential for the django server to restart when library modules are updated.
)

# production pex packages should used the default layout of 'zipped'
pex_binary(
    name="manage_prod",
    entry_point="manage.py:main",
    dependencies=[
        ":src",
    ]
)