## firestore and inappmessaging protobuf dependecy for java management

This repo is in response to issues encountered when transitioning to firebase firestore and inappmessaging. 
These firebase projects rely on protobuf-lite causes issues for protobuf-java (protobuf-javalite) dependent projects.

Here are some issues reported in the community related to this workaround:

- [Git 7094](https://github.com/protocolbuffers/protobuf/issues/7094)
- [Git 1889](https://github.com/protocolbuffers/protobuf/issues/1889)
- [Git 5608](https://github.com/googleapis/google-cloud-java/issues/5608)
- [Git 25](https://github.com/googleapis/java-dialogflow/issues/25)


### Getting started
Clone this project:

```
git clone https://github.com/gitprelimtek/protobuf-javalite-firebase-wellknowntypes.git
```

** If you have special version requirements, edit the pom.xml file to reflect the artifact versions you require. **

### Create the fatjar
Run the bash script

```
cd protobuf-javalite-firebase-wellknowntypes/
./run.sh
ls -l ./output
```

If successful fatjar will be in output directory.

### Import the fatjar into android studio

1. Copy the fatjar into your Android studio project lib directory. 
2. Update the app build.gradle dependencies:

```
implementation 'com.google.firebase:firebase-firestore:21.4.0'
implementation files('libs/ptek-protobuf-javalite-firebase-wellknowntypes.jar')
```

3. Recompile.

