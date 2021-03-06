GPG cheat-sheet
  keys:
    genkey: --gen-key
      for genentropy: 
        dd if=/dev/vda of=/dev/zero
        or yum install rng-tools && service rngd start (adding in
        /etc/sysconfig/rngd '-r /dev/urandom' for EXTRAOPTS)
    export pubkey: --export -a "User Name" > public.key
    export prvkey: gpg --export-secret-key -a "User Name" > private.key
      --export-secret-keys key-id > private_key
      --export-secret-keys EE74D48D > private_key
    export to keyserver:
      --keyserver servername --send-keys key-id
      --keyserver keyserver.ubuntu.com --send-keys EE74D48D
    import pubkey: gpg --import public.key
    import prvkey: gpg --allow-secret-key-import --import private.key
      while importing it's good to validate fingerprint with 'gpg --edit-key
        somekey.pub' and than:
          - fpr (displays fingerprint)
          - sign (signs - u could first verify with owner via phone)
          - check (double check after signing)
    remove pubkey from pubkeyring: gpg --delete-key "User Name"
    remove prvkey from prvkeyring: gpg --delete-secret-key "User Name"
    list pubkeys: gpg --list-keys
    list prvkeys: gpg --list-secret-keys
    revoke:
      first gen. revoc. cert: --output revocation_cert.asc --gen-revoke EE74D48D
      than import it: --import revocation_cert.asc
      and update keysrv: --keyserver keyserver.ubuntu.com --send-keys EE74D48D
  encrypt / decrypt (assymetric):
    encrypt data:
      -e -u "Sender User Name" -r "Receiver User Name" document.doc
        -u (secret)
        -r (recipient pubkey)
      --output document.doc.gpg --encrypt --recipient somewhone@somewhere.com document.doc
    decrypt: 
      -o document.doc -d document.doc.gpg
      --output document.doc --decrypt document.doc.gpg
  encrypt / decrypt (symmetric):
    In ~/gnupg/gpg.conf:
      cipher-algo AES256
    encrypt:
      --output document.doc.gpg --symmetric document.doc
        --cipher-algo CAMELLIA256|TWOFISH|AES256|CAST5 (def)|...
        check available algos with gpg --version
        --armor - for ascii-armor
        --sign for signing with prvkey
    decrypt:
      -o document.doc -d document.doc.gpg
  sign msg:
      --clearsign document.txt
      --clearsign --detach-sign document.txt (with detaching signature)
      -- verify document.txt.asc (verifying)
