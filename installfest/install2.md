# Mac OSX - 2

## Node

To install Node

```text
brew install node
```

Verify the installation afterwards by running

```text
node -v
npm -v
```

The above should display without any errors.

To finish up your installation, run this command to allow for global installations of npm tools.

```text
sudo chown -R $USER /usr/local/lib
```

## [Postgres](install2.md#postgres)

### Postgres.app

We will be using a relational database called Postgres for Node and Rails portion our class.

Download and install from [http://postgresapp.com/](http://postgresapp.com/)

Get the version of Postgres being installed on your system:

```text
ls -la /Applications/Postgres.app/Contents/Versions
```

There should be only one version in this directory, or take the highest version.

Create the export path command with that version number/directory name

```text
export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/9.5/bin
```

If you have successfully configured bash and sublime, the following command should work.

```text
sublime ~/.profile
```

Your sublime editor will popup with configuration settings, at the bottom of the file append the same line:

```text
export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/9.5/bin
```

Type `which psql` at which point should display

```text
/Applications/Postgres.app/Contents/Versions/9.5/bin/psql
```

## Install some other sublime packages:

* Babel \(syntax definition, we'll use this when working with React\)

