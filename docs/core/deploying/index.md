---
title: "Implementación de aplicaciones .NET Core"
description: "Implementación de aplicaciones .NET Core"
keywords: ".NET, .NET Core, implementación de .NET Core"
author: rpetrusha
manager: wpickett
ms.date: 09/08/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
translationtype: Human Translation
ms.sourcegitcommit: 663f4102b82512e64ab39d8046c7298a7cf37de7
ms.openlocfilehash: 96eb2cc7ca948b3e372fa1363b1741624d791d27

---

# <a name="net-core-application-deployment"></a>Implementación de aplicaciones .NET Core #

Puede crear dos tipos de implementaciones para aplicaciones .NET Core: 

- Implementación dependiente de Framework. Como su nombre indica, la implementación dependiente de Framework (FDD) se basa en la presencia de una versión compartida de .NET Core en todo el sistema en el sistema de destino. Como .NET Core ya está presente, la aplicación también es portátil entre instalaciones de .NET Core. La aplicación solo contiene su propio código y dependencias de terceros que están fuera de las bibliotecas .NET Core. FDD contiene archivos .dll que se pueden iniciar utilizando la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos. Por ejemplo, `dotnet app.dll` ejecuta una aplicación denominada `app`.

- Implementación autocontenida. A diferencia de FDD, una implementación autocontenida (SCD) no depende de que los componentes compartidos estén presentes en el sistema de destino. Todos los componentes, incluidas las bibliotecas y el entorno de ejecución de .NET Core, se incluyen con la aplicación y están aislados de otras aplicaciones .NET Core. Las SCD incluyen un archivo ejecutable (como `app.exe` en plataformas de Windows para una aplicación denominada `app`), que es una versión con otro nombre del host de .NET Core específico de la plataforma y un archivo .dll (como `app.dll`), que es la aplicación real.

## <a name="frameworkdependent-deployments-fdd"></a>Implementaciones dependientes de Framework (FDD) ##

En una FDD, solo se implementa su aplicación y cualquier dependencia de terceros. No tiene que implementar .NET Core, puesto que la aplicación usará la versión de .NET Core que esté presente en el sistema de destino. Este es el modelo de implementación predeterminado para aplicaciones .NET Core.

### <a name="why-create-a-frameworkdependent-deployment"></a>¿Por qué crear una implementación dependiente del marco? ###

La implementación de FDD tienen varias ventajas:

- No es necesario definir por adelantado los sistemas operativos de destino en los que se ejecutará la aplicación .NET Core. Como .NET Core usa un formato de archivo PE común para archivos ejecutables y bibliotecas independientemente del sistema operativo, .NET Core puede ejecutar la aplicación con independencia del sistema operativo subyacente. Para más información sobre el formato de archivo PE, consulte [.NET Assembly File Format](../../standard/assembly-format.md) (Formato de archivo de ensamblado .NET).

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino, o una versión posterior, ya está instalada en el sistema host.

- Es posible que el entorno de tiempo de ejecución y las bibliotecas .NET Core cambien en futuras versiones sin su conocimiento. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación.

### <a name="deploying-a-frameworkdependent-deployment"></a>Implementación de una implementación dependiente del marco ###

La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. En el ejemplo se usa la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos; sin embargo, también puede usar un entorno de desarrollo, como Visual Studio o Visual Studio Code para compilar, probar y publicar el ejemplo.

1. Cree un directorio para el proyecto y, en la línea de comandos, escriba [dotnet new](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C#.

2. Abra el archivo `Program.cs` en un editor y reemplace el código generado automáticamente por el código siguiente. Se pide al usuario que escriba texto y, a continuación, se muestran las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else
              {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) para restaurar las dependencias especificadas en el proyecto.

4. Cree una compilación de depuración de su aplicación mediante el comando [dotnet build](../tools/dotnet-build.md).

5. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación mediante el comando `dotnet publish -f netcoreapp1.0 -c release`. Con esto se crea una versión (en lugar de una depuración) de la aplicación.

   Los archivos resultantes se colocan en un directorio llamado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netcoreapp1.0` del proyecto.

6. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.

Además de los archivos binarios de la aplicación, el instalador debe también empaquetar el programa de instalación de un marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.  La instalación del marco compartido requiere acceso raíz o de administrador dado que implica a toda la máquina.

### <a name="deploying-a-frameworkdependent-deployment-with-thirdparty-dependencies"></a>Implementación de una implementación dependiente del marco con dependencias de terceros ###

La implementación de una implementación dependiente del marco con una o varias dependencias de terceros implica tres pasos adicionales antes de ejecutar el comando `dotnet restore`:

1. Agregue referencias a las bibliotecas de terceros a la sección `dependencies` de su archivo `project.json`. La siguiente sección `dependencies` usa Json.NET como biblioteca de terceros.

    ```json
    "dependencies": {
      "Microsoft.NETCore.App": {
        "type": "platform",
        "version": "1.0.0"
      },
      "Newtonsoft.Json": "9.0.1"
    },
    ```

2. Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros. Para descargar el paquete, ejecute el comando `dotnet restore` después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

Tenga en cuenta que una implementación dependiente del marco con dependencias de terceros solo será tan portátil como sus dependencias de terceros. Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se podrá portar a sistemas Windows. Esto puede ocurrir si la dependencia de terceros propiamente dicha depende del código nativo. Un buen ejemplo de ello es el servidor Kestrel. Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contendrá una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md#what-are-rids) que admita la dependencia nativa (y que exista en su paquete de NuGet).

## <a name="selfcontained-deployments-scd"></a>Implementaciones autocontenidas (SCD) ##

En una implementación autocontenida, no solo implementa su aplicación y cualquier dependencia de terceros, sino también la versión de .NET Core con la que compila la aplicación. La creación de una SCD no incluye, sin embargo, las [dependencias nativas de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) propiamente dichas en diversas plataformas (por ejemplo, OpenSSL en macOS) así que es necesario instalarlas antes de ejecutar la aplicación. 

### <a name="why-deploy-a-selfcontained-deployment"></a>¿Por qué realizar una implementación autocontenida? ###

La implementación de una implementación autocontenida tiene dos ventajas principales:

- Tiene el control exclusivo de la versión de .NET Core que se implementa con la aplicación. El mantenimiento de .NET Core solo puede realizarlo usted.

- Puede tener la seguridad de que el sistema de destino puede ejecutar su aplicación de .NET Core, dado que usted proporciona la versión de .NET Core en la que se ejecuta.

También tiene algunos inconvenientes:

- Como .NET Core se incluye en el paquete de implementación, debe seleccionar por adelantado las plataformas de destino en las que se compilan los paquetes de implementación.

- El tamaño de su paquete de implementación es relativamente grande, ya que tendrá que incluir .NET Core, así como la aplicación y sus dependencias de terceros.

- La implementación de numerosas aplicaciones .NET Core autocontenidas en un sistema puede consumir importantes cantidades de espacio en disco, puesto que cada aplicación duplica archivos de .NET Core.

### <a name="a-namesimpleselfa-deploying-a-simple-selfcontained-deployment"></a>Implementación de una implementación autocontenida sencilla ###

La implementación de una implementación autocontenida sin dependencias de terceros implica crear el proyecto, modificar el archivo project.json y compilar, probar y publicar la aplicación.  Un sencillo ejemplo escrito en C# ilustra el proceso. En el ejemplo se usa la utilidad `dotnet` desde la línea de comandos; sin embargo, también puede usar un entorno de desarrollo, como Visual Studio o Visual Studio Code para compilar, probar y publicar el ejemplo.

1. Cree un directorio para el proyecto y, en la línea de comandos, escriba `dotnet new` para crear un nuevo proyecto de consola de C#.

2. Abra el archivo `Program.cs` en un editor y reemplace el código generado automáticamente por el código siguiente. Se pide al usuario que escriba texto y, a continuación, se muestran las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Abra el archivo `project.json` y quita la línea siguiente de la sección `frameworks`:

   ```json
   "type": "platform",
   ```
La sección Framework debe aparecer de la manera siguiente una vez modificada:

    ```json
    "frameworks": {
      "netcoreapp1.0": {
        "dependencies": {
          "Microsoft.NETCore.App": {
             "version": "1.0.0"
          }
        }
      }
    }
    ```
Al quitar el atributo `"type": "platform"` se indica que el marco se proporciona como un conjunto de componentes locales a nuestra aplicación, y no como un paquete de plataforma de todo el sistema.

4. Cree una sección `runtimes` en el archivo `project.json` que defina las plataformas a las que se dirige su aplicación, y especifique el identificador de tiempo de ejecución de cada una. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). Por ejemplo, la siguiente sección `runtimes` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.10 de 64 bits.

    ```json
        "runtimes": {
          "win10-x64": {},
          "osx.10.10-x64": {}
        }
    ```
Tenga en cuenta también de que debe agregar una coma para separar la sección `runtimes` de la sección anterior.
Más adelante en esta sección aparece un ejemplo completo del archivo `project.json`.

6. Ejecute el comando `dotnet restore` para restaurar las dependencias especificadas en el proyecto.

7. Cree compilaciones de depuración de la aplicación en cada plataforma de destino mediante el comando `dotnet build`. A menos que especifique el identificador de tiempo de ejecución que desea quiere compilar, el comando `dotnet build` crea una compilación solo para el ID de tiempo de ejecución actual del sistema. Puede compilar la aplicación para ambas plataformas de destino con los comandos:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.10-x64
    ```
Las compilaciones de depuración de la aplicación para cada plataforma se encontrarán en el directorio `.\bin\Debug\netcoreapp1.0\<runtime_identifier>` del proyecto.

8. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación para cada plataforma de destino mediante la ejecución del comando `dotnet publish` en ambas plataformas de destino, de la manera siguiente:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.10-x64
   ```
Se crea una versión de lanzamiento (en lugar de una depuración) de la aplicación para cada plataforma de destino. Los archivos resultantes se colocan en un subdirectorio denominado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netcoreapp1.0\<runtime_identifier>` del proyecto. Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.

9. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

Los archivos publicados se pueden implementar de la forma que desee. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. 

El siguiente es el archivo `project.json` completo para este proyecto.

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable",
    "emitEntryPoint": true
  },
  "dependencies": {},
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "version": "1.0.0"
        }
      }
    }
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.10-x64": {}
  }
}
```

### <a name="deploying-a-selfcontained-deployment-with-thirdparty-dependencies"></a>Implementación de una implementación autocontenida con dependencias de terceros ###

Implementar una implementación autocontenida con una o varias dependencias de terceros implica agregar la dependencia de terceros:

1. Agregue referencias a las bibliotecas de terceros a la sección `dependencies` de su archivo `project.json`. La siguiente sección `dependencies` usa Json.NET como biblioteca de terceros.

    ```json
    "dependencies": {
      "Microsoft.NETCore.App": "1.0.0",
      "Newtonsoft.Json": "9.0.1"
    },
    ```
2. Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema. Para que la dependencia esté disponibles para la aplicación, ejecute el comando `dotnet restore` después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

El siguientes es el archivo project.json completo para este proyecto:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable",
    "emitEntryPoint": true
  },
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0",
    "Newtonsoft.Json": "9.0.1"
  },
  "frameworks": {
    "netcoreapp1.0": {
    }
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.10-x64": {}
  }
}
```

Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación. Las bibliotecas de terceros no están aún presentes en el sistema en el que se ejecuta la aplicación.

Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca. Esto es parecido a tener dependencias de terceros con dependencias nativas en la implementación dependiente del marco. 

### <a name="deploying-a-selfcontained-deployment-with-a-smaller-footprint"></a>Implementación de una implementación autocontenida con una superficie menor ###

Si la disponibilidad de espacio de almacenamiento adecuado en sistemas de destino puede ser un problema, puede reducir la superficie general de la aplicación excluyendo algunos componentes del sistema. Para ello, defina explícitamente los componentes de .NET Core que incluye su aplicación en su archivo project.json.

Para crear una implementación autocontenida con una superficie menor, comience siguiendo los dos primeros pasos para crear una implementación autocontenida. Cuando haya ejecutado el comando `dotnet new` y agregado el código fuente de C# a la aplicación, haga lo siguiente:

1. Abra el archivo `project.json` y reemplace la sección `frameworks` por lo siguiente:

    ```json
    "frameworks": {
      "netstandard1.6": { }
    }
    ```
Esto hace dos cosas:

    * Indica que, en lugar de usar el marco entero `netcoreapp1.0`, que incluye .NET Core CLR, la biblioteca .NET Core y varios otros componentes del sistema, la aplicación emplea solamente a la biblioteca estándar. NET.

    * Al quitar el atributo `"type": "platform"` se indica que el marco se proporciona como un conjunto de componentes locales a nuestra aplicación, y no como un paquete de plataforma de todo el sistema.

2. Reemplace la sección `dependencies` por lo siguiente:

    ```json
    "dependencies": {
      "NETStandard.Library": "1.6.0",
      "Microsoft.NETCore.Runtime.CoreCLR": "1.0.2",
      "Microsoft.NETCore.DotNetHostPolicy":  "1.0.1"
    },
    ```
   Esto define los componentes del sistema usados por nuestra aplicación. Los componentes del sistema empaquetados con nuestra aplicación incluyen la biblioteca estándar. NET, el entorno de tiempo de ejecución de .NET Core y el host de .NET Core. Esto produce una implementación autocontenida con una superficie menor.

3. Al igual que hizo en el ejemplo `runtimes`Implementación de una implementación autocontenida sencilla`project.json`, cree una sección [ en el archivo ](#simpleSelf) que defina las plataformas a las que se dirige su aplicación, y especifique el identificador de tiempo de ejecución de cada una. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). Por ejemplo, la siguiente sección `runtimes` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.10 de 64 bits.

    ```json
        "runtimes": {
          "win10-x64": {},
          "osx.10.10-x64": {}
        }
    ```
Tenga en cuenta también de que debe agregar una coma para separar la sección `runtimes` de la sección anterior.
Más adelante en esta sección aparece un ejemplo completo del archivo `project.json`.

4. Ejecute el comando `dotnet restore` para restaurar las dependencias especificadas en el proyecto.

5. Cree compilaciones de depuración de la aplicación en cada plataforma de destino mediante el comando `dotnet build`. A menos que especifique el identificador de tiempo de ejecución que desea quiere compilar, el comando `dotnet build` crea una compilación solo para el ID de tiempo de ejecución actual del sistema. Puede compilar la aplicación para ambas plataformas de destino con los comandos:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.10-x64
    ```

6. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación para cada plataforma de destino mediante la ejecución del comando `dotnet publish` en ambas plataformas de destino, de la manera siguiente:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.10-x64
   ```
Se crea una versión de lanzamiento (en lugar de una depuración) de la aplicación para cada plataforma de destino. Los archivos resultantes se colocan en un subdirectorio denominado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netstandard1.6\<runtime_identifier>` del proyecto. Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.

7. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

Los archivos publicados se pueden implementar de la forma que desee. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. 

El siguiente es el archivo `project.json` completo para este proyecto.

```json
   {
     "version": "1.0.0-*",
     "buildOptions": {
       "debugType": "portable",
       "emitEntryPoint": true
     },
     "dependencies": {
       "NETStandard.Library": "1.6.0",
       "Microsoft.NETCore.Runtime.CoreCLR": "1.0.2",
       "Microsoft.NETCore.DotNetHostPolicy":  "1.0.1"
     },
     "frameworks": {
       "netstandard1.6": { }
     },
     "runtimes": {
       "win10-x64": {},
       "osx.10.10-x64": {}
     }
   }
```



<!--HONumber=Nov16_HO1-->


