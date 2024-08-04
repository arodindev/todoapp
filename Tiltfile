# Backend 'taskapp' with live update

repo_root = os.path.dirname(__file__)
src_dir = os.path.join(repo_root, 'todoapp')
trigger_file = os.path.join(src_dir, 'pyproject.toml')
docker_file = os.path.join(repo_root, 'docker', 'Dockerfile')
docker_compose_file = os.path.join(repo_root, 'docker', 'docker-compose.yaml')

docker_compose(docker_compose_file)
docker_build('ghcr.io/arodindev/todoapp', repo_root,
    dockerfile=docker_file,
    live_update=[
        sync(src_dir, '/todoapp/todoapp'),
        run("cd /todoapp/todoapp && poetry install", trigger=trigger_file),
        restart_container()
    ]
)

