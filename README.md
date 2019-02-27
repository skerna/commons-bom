# GRADLE JAVA PLATFORM

Este componente Gradle Platform para al gestión de versiones en un entorno multiproject
generando un BOM (BILL of materials)

### Como usar esto

Este proyecto te evitar estar especificando versiones de las librerias y sus 
dependencias 


```groovy
    
    api platform("io.skerna.libs:skerna-platform:${version}")
    
    // Consumir skerna SLOGS para JVM (Ya no es necesario especificar la versión)
    implementation("io.skerna.libs:skerna-slogs-jvm")
```

### Crear nuevas librerías

#### 1) Añade el proyecto a LIBSMETA REPO usando el archivo .meta

```json
{
  "projects": {
    "./skerna-slbase":"git@gitlab.com:skerna/skerna-libs/skerna-slbase.git",
    "./skerna-sansi": "git@gitlab.com:skerna/skerna-libs/skerna-sansi.git",
    "./skerna-slog": "git@gitlab.com:skerna/skerna-libs/skerna-slog.git",
    "./skerna-sfutures": "git@gitlab.com:skerna/skerna-libs/skerna-sfutures.git",
    "./skerna-octopus": "git@gitlab.com:skerna/skerna-libs/skerna-octopus.git",
    "./skerna-sreval": "git@gitlab.com:skerna/skerna-libs/skerna-sreval.git",
    "./skerna-i18nexceptions": "git@gitlab.com:skerna/skerna-libs/skerna-i18nexceptions.git",
    "./skerna-shield": "git@gitlab.com:skerna/skerna-libs/skerna-shield.git",
    "./skerna-dsql": "git@gitlab.com:skerna/skerna-libs/skerna-dsql.git",
    "./skerna-bolt": "git@gitlab.com:skerna/skerna-libs/skerna-bolt.git",
    "./skerna-platform": "git@gitlab.com:skerna/skerna-libs/skerna-platform.git",
    "./NEWLIB": "SOME_GITDIR"
  }
}
```


#### 2) Comparte la libreria en BillOfMaterial

Para ellos solamente debes agregar la nueva libreria como dependecias en el archivo
build.gradle

```groovy
    api "io.skerna.libs:skerna-NEWLIB:$version"
```


