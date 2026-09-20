name: Build Legend Recorder

on:
  push:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Set up JDK 21
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 21

      - name: Set up Gradle 8.10.2
        uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: 8.10.2

      - name: Build mod jar
        run: gradle build --no-daemon

      - name: Upload mod jar
        uses: actions/upload-artifact@v4
        with:
          name: legend-recorder-1.0.0
          path: build/libs/*.jar
          if-no-files-found: error
