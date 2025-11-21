# Examination 1 - Understanding SSH and public key authentication

Connect to one of the virtual lab machines through SSH, i.e.

    $ ssh -i deploy_key -l deploy webserver

Study the `.ssh` folder in the home directory of the `deploy` user:

    $ ls -ld ~/.ssh

Look at the contents of the `~/.ssh` directory:

    $ ls -la ~/.ssh/

## QUESTION A

What are the permissions of the `~/.ssh` directory?

Svar: 700 (drwx-------)

Why are the permissions set in such a way?

Svar: Endast ägaren har läs,skriv och körbehörighet. Detta görs av säkerhetsskäl då SSH-privata nycklar ska hållas hemliga för att ingen oberhörig ska komma åt dem. 

## QUESTION B

What does the file `~/.ssh/authorized_keys` contain?

Svar:Filen innehåller den publika ssh-nyckeln för den användare/maskin som tillåts logga in som deploy utan lösenord.

## QUESTION C

When logged into one of the VMs, how can you connect to the
other VM without a password?

Svar: Jag genererade ett ssh-nyckelpar för användaren deploy på webservern och kopierade sedan den publika nyckeln manuellt till dbserverns "authorized keys".

### Hints:

* man ssh-keygen(1)
* ssh-copy-id(1) or use a text editor

## BONUS QUESTION

Can you run a command on a remote host via SSH? How?
