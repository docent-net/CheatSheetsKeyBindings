Docker cheat-sheet:
  - managing cnts:
    - run (create cnt)
        -rm - will run and remove after it stops
    - stop/start/restart
      - poking around image: docker run -t -i <some_shell>
      - mapping dir: docker run -v $HOSTDIR:$DOCKERDIR
    - rm - deletes cnt
    - kill - sends SIGKILL to container
    - attach - connects to container
    - wait - blocks until container stops
    - ps - show running containers
      -a - all: running and stopped
  - containers data / info:
    - inspect - cnt info
    - logs - get cnt logs
    - port - show ports info (public)
    - top - show running cnt's procs
    - diff - show changed files in cnt's FS
  - FS
    - cp - copies files from cnt (one way)
    - export - creates cnt's tarball
    - enter FS (withous SSH via nsenter):
      nsenter -m -u -n -i -p -t 2217 /bin/bash
        where 2217 is containers PID taken from:
        docker inspect --format '{{ .State.Pid }}' a711c7ab0420
