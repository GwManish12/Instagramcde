name: Android CI
on:
 push:
   branches: [master]
 pull_request:
   branches: [master]


jobs:
 build:
   runs-on: ubuntu-latest
   steps:
     – name: Checkout
       uses: actions/checkout@v2.4.0
     – name: Setup JDK
       uses: actions/setup-java@v2.5.0
       with:
         distribution: ‘temurin’
         java-version: ’11’
     – name: Set execution flag for gradlew
       run: chmod +x gradlew
     – name: Build with Gradle
       run: ./gradlew build
