# ansible
Ansible은 IT 자동화 도구이다. Ansible의 동작은 다음의 세 가지 요소를 통해 이루어 진다.
- inventory
- playbook
- module

## inventory
inventory에서는 ssh 접근 ip, linux user, private key 등 서버의 접속 정보를 정의한다. 

## playbook
playbook은 inventory에서 명시된 서버에서 무엇을 해야할 지를 담고있다. 파일의 형식은 yaml이다.  

### 실행
```zsh
> ansible-playbook -i <inventory_file_name> <playbook_file_name.yaml>
```

### 작성 예시
```yaml
---

- host: all
  become: true

  vars:
    text: hello world

  tasks: 
    - name: task name
      shell: pwd
```

## module
module은 playbook에서 각 task가 어떻게 수행될 지를 나타낸다. 위의 playbook 작성 예시에서 사용된 shell module은 shell을 통해 명령어를 실행시키는 역할을 한다. 