---
title: Publicación de aplicaciones
description: Obtenga más información sobre las formas de publicar una aplicación de .NET Core. .NET Core puede publicar aplicaciones específicas de la plataforma o multiplataforma. Puede publicar una aplicación como independiente o como dependiente de la plataforma. Cada modo afecta a la forma en la que un usuario ejecuta la aplicación.
ms.date: 04/01/2020
ms.openlocfilehash: ece5e46162fd4a8de0b996ba239e89cceca4dbca
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720116"
---
# <a name="net-core-application-publishing-overview"></a>Información general sobre la publicación de aplicaciones de .NET Core

Las aplicaciones que se crean con .NET Core se pueden publicar de dos modos diferentes, lo cual afecta a la forma en la que un usuario ejecuta la aplicación.

La publicación de la aplicación como *independiente* genera una aplicación que incluye el entorno de ejecución y las bibliotecas de .NET Core, así como la aplicación y sus dependencias. Los usuarios de la aplicación pueden ejecutarla en un equipo que no tenga instalado el entorno de ejecución de .NET Core.

La publicación de la aplicación como *dependiente de la plataforma* genera una aplicación que incluye únicamente la propia aplicación y sus dependencias. Los usuarios de la aplicación tienen que instalar el entorno de ejecución de .NET Core por separado.

De forma predeterminada, ambos modos de publicación generan un archivo ejecutable específico de la plataforma. Las aplicaciones dependientes de la plataforma se pueden crear sin un archivo ejecutable y son multiplataforma.

Cuando se genera un archivo ejecutable, puede especificar la plataforma de destino con un identificador de entorno de ejecución (RID). Para obtener más información sobre los RID, vea el [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

En la tabla siguiente se describen los comandos que se usan para publicar una aplicación como dependiente de la plataforma o independiente según la versión del SDK:

| Tipo                                                                                     | SDK 2.1 | SDK 3.x | Comando |
| ---------------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [archivo ejecutable dependiente de la plataforma](#publish-framework-dependent) para la plataforma actual. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [archivo ejecutable dependiente de la plataforma](#publish-framework-dependent) para una plataforma específica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [archivo binario multiplataforma dependiente de la plataforma](#publish-framework-dependent).               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [archivo ejecutable independiente](#publish-self-contained)                                    | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

Para obtener más información, vea el artículo sobre el [comando dotnet publish de .NET Core](../tools/dotnet-publish.md).

## <a name="produce-an-executable"></a>Generación de un archivo ejecutable

Los archivos ejecutables no son multiplataforma. Son específicos de un sistema operativo y de la arquitectura de la CPU. Al publicar la aplicación y crear un archivo ejecutable, puede publicarla como [independiente](#publish-self-contained) o [dependiente de la plataforma](#publish-framework-dependent). La publicación de una aplicación como independiente incluye el entorno de ejecución de .NET Core con la aplicación, y los usuarios de la aplicación no tienen que preocuparse de instalar .NET Core antes de ejecutar la aplicación. Las aplicaciones publicadas como dependientes de la plataforma no incluyen el entorno de ejecución ni las bibliotecas de .NET Core; solo se incluyen la aplicación y las dependencias de terceros.

Los siguientes comandos generan un archivo ejecutable:

| Tipo                                                                                     | SDK 2.1 | SDK 3.x | Comando |
| ---------------------------------------------------------------------------------------- | ------- | ------- | ------- |
| [archivo ejecutable dependiente de la plataforma](#publish-framework-dependent) para la plataforma actual. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [archivo ejecutable dependiente de la plataforma](#publish-framework-dependent) para una plataforma específica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [archivo ejecutable independiente](#publish-self-contained)                                    | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

## <a name="produce-a-cross-platform-binary"></a>Generación de un archivo binario multiplataforma

Los archivos binarios multiplataforma se crean al publicar la aplicación como [dependiente de la plataforma](#publish-framework-dependent) en forma de un archivo *.dll*. El archivo *.dll* tiene el nombre del proyecto. Por ejemplo, si tiene una aplicación denominada **lector_de_palabras**, se creará un archivo denominado *lector_de_palabras.dll*. Las aplicaciones publicadas de este modo se ejecutan con el comando `dotnet <filename.dll>` y se pueden ejecutar en cualquier plataforma.

Los archivos binarios multiplataforma se pueden ejecutar en cualquier sistema operativo siempre que ya esté instalado el entorno de ejecución de .NET Core de destino. Si el entorno de ejecución de .NET Core de destino no está instalado, la aplicación puede ejecutarse con un entorno de ejecución más reciente a condición de que la aplicación esté configurada para la puesta al día. Para más información, consulte [Puesta al día de las aplicaciones dependientes de la plataforma](../versions/selection.md#framework-dependent-apps-roll-forward).

El siguiente comando genera un archivo binario multiplataforma:

| Tipo                                                                                 | SDK 2.1 | SDK 3.x | Comando |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [archivo binario multiplataforma dependiente de la plataforma](#publish-framework-dependent).           | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |

## <a name="publish-framework-dependent"></a>Publicación como dependiente de la plataforma

Las aplicaciones publicadas como dependientes de la plataforma son multiplataforma y no incluyen el entorno de ejecución de .NET Core. El usuario de la aplicación debe instalar el entorno de ejecución de .NET Core.

La publicación de una aplicación como dependiente de la plataforma genera un [archivo binario multiplataforma](#produce-a-cross-platform-binary) como archivo *.dll* y un [archivo ejecutable específico de la plataforma](#produce-an-executable) que tiene como destino la plataforma actual. El archivo *.dll* es multiplataforma, pero el ejecutable no lo es. Por ejemplo, si publica una aplicación denominada **lector_de_palabras** y el destino es Windows, se creará un archivo ejecutable *lector_de_palabras.exe* junto con *lector_de_palabras.dll*. Si el destino es Linux o macOS, se creará un archivo ejecutable *lector_de_palabras* junto con *lector_de_palabras.dll*. Para obtener más información sobre los RID, vea el [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

> [!IMPORTANT]
> El SDK 2.1 de .NET Core no genera archivos ejecutables específicos de la plataforma al publicar una aplicación dependiente de la plataforma.

El archivo binario multiplataforma de la aplicación se puede ejecutar con el comando `dotnet <filename.dll>` en cualquier plataforma. Si la aplicación usa un paquete NuGet que tenga implementaciones específicas de la plataforma, se copiarán todas las dependencias de la plataforma en la carpeta de publicación junto con la aplicación.

Puede crear un archivo ejecutable para una plataforma específica pasando los parámetros `-r <RID> --self-contained false` al comando [`dotnet publish`](../tools/dotnet-publish.md). Si se omite el parámetro `-r`, se creará un archivo ejecutable para la plataforma actual. Los paquetes NuGet que tengan dependencias específicas de la plataforma para la plataforma de destino se copiarán en la carpeta de publicación.

### <a name="advantages"></a>Ventajas

- **Implementación de pequeño tamaño**\
En este caso solo se distribuyen la aplicación y sus dependencias. El usuario instala el entorno de ejecución y las bibliotecas de .NET Core, y todas las aplicaciones comparten ese entorno de ejecución.

- **Multiplataforma**\
La aplicación y cualquier biblioteca basada en .NET se ejecuta en otros sistemas operativos. No necesita definir una plataforma de destino para la aplicación. Para obtener más información sobre el formato de archivo de .NET, consulte [Formato de archivo de ensamblado .NET](../../standard/assembly/file-format.md).

- **Uso del entorno de ejecución revisado más reciente**\
La aplicación usa el entorno de ejecución más reciente (dentro de la familia principal y secundaria de .NET Core de destino) instalada en el sistema de destino. De esta forma, la aplicación utilizará automáticamente la versión revisada más reciente del entorno de ejecución de .NET Core. Este comportamiento predeterminado se puede anular. Para más información, consulte [Puesta al día de las aplicaciones dependientes de la plataforma](../versions/selection.md#framework-dependent-apps-roll-forward).

### <a name="disadvantages"></a>Desventajas

- **Preinstalación necesaria del entorno de ejecución**\
Su aplicación solo se puede ejecutar si la versión de .NET Core de destino de la aplicación ya está instalada en el sistema host. Puede configurar el comportamiento de puesta al día para que la aplicación requiera una versión específica de .NET Core o permita el uso de una versión más reciente de .NET Core. Para más información, consulte [Puesta al día de las aplicaciones dependientes de la plataforma](../versions/selection.md#framework-dependent-apps-roll-forward).

- **Cambios posibles de .NET Core**\
Es posible actualizar el entorno de ejecución y las bibliotecas de .NET Core en el equipo donde se ejecuta la aplicación. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación si usa las bibliotecas de .NET Core, lo que sucede con la mayoría de las aplicaciones. Puede configurar de qué modo la aplicación usa versiones más recientes de .NET Core. Para más información, consulte [Puesta al día de las aplicaciones dependientes de la plataforma](../versions/selection.md#framework-dependent-apps-roll-forward).

La desventaja siguiente solo se aplica al SDK 2.1 de .NET Core.

- **Uso del comando `dotnet` para iniciar la aplicación**\
Los usuarios deben ejecutar el comando `dotnet <filename.dll>` para iniciar la aplicación. El SDK 2.1 de .NET Core no genera archivos ejecutables específicos de la plataforma para las aplicaciones que se publiquen como dependientes de la plataforma.

### <a name="examples"></a>Ejemplos

Sirve para publicar una aplicación multiplataforma dependiente de la plataforma. Se creará un archivo ejecutable que tendrá como destino la plataforma actual junto con el archivo *.dll*.

```dotnet
dotnet publish
```

Sirve para publicar una aplicación multiplataforma dependiente de la plataforma. Se creará un ejecutable de 64 bits de Linux junto con el archivo *.dll*. Este comando no funciona con .NET Core SDK 2.1.

```dotnet
dotnet publish -r linux-x64 --self-contained false
```

## <a name="publish-self-contained"></a>Publicación como independiente

La publicación de la aplicación como independiente genera un archivo ejecutable específico de la plataforma. La carpeta de publicación de salida contiene todos los componentes de la aplicación, incluidas las bibliotecas y el entorno de ejecución de destino de .NET Core. La aplicación está aislada de otras aplicaciones de .NET Core y no usa un entorno de ejecución compartido instalado localmente. No es necesario que el usuario de la aplicación descargue e instale .NET Core.

El archivo binario ejecutable se genera para la plataforma de destino especificada. Por ejemplo, si tiene una aplicación denominada **lector_de_palabras** y publica un archivo ejecutable independiente para Windows, se creará el archivo *lector_de_palabras.exe*. Si se publica para Linux o macOS, se creará el archivo *lector_de_palabras*. La plataforma y la arquitectura de destino se especifican con el parámetro `-r <RID>` para el comando [`dotnet publish`](../tools/dotnet-publish.md). Para obtener más información sobre los RID, vea el [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

Si la aplicación tiene dependencias específicas de la plataforma, como un paquete NuGet que contenga tales dependencias, se copiarán en la carpeta de publicación junto con la aplicación.

### <a name="advantages"></a>Ventajas

- **Control de la versión de .NET Core**\
Puede controlar qué versión de .NET Core se implementa con la aplicación.

- **Destinatarios específicos de la plataforma**\
Como tiene que publicar la aplicación para cada plataforma, sabe dónde se ejecutará. Si .NET Core introduce una nueva plataforma, los usuarios no podrán ejecutar la aplicación en ella hasta que publique una versión que tenga esa plataforma como destino. Puede probar la aplicación para buscar problemas de compatibilidad antes de que los usuarios la ejecuten en la nueva plataforma.

### <a name="disadvantages"></a>Desventajas

- **Implementaciones de mayor tamaño**\
Dado que la aplicación incluye el entorno de ejecución de .NET Core y todas las dependencias de la aplicación, el tamaño de descarga y el espacio de disco duro necesario es mayor que en el caso de una versión [dependiente de la plataforma](#publish-framework-dependent).

  > [!TIP]
  > Puede reducir el tamaño de la implementación en sistemas Linux en 28 MB aproximadamente con el [*modo invariable global*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) de .NET Core. Esto obliga a la aplicación a tratar todas las referencias culturales como la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

  > [!TIP]
  > Hay una [característica de recorte en versión preliminar](trim-self-contained.md) que puede ayudar a reducir todavía más el tamaño de su desarrollo.

- **Mayor dificultad para actualizar la versión de .NET Core**\
El entorno de ejecución de .NET Core (distribuido con la aplicación) solo se puede actualizar mediante la publicación de una nueva versión de la aplicación. Sin embargo, .NET Core actualizará las revisiones de seguridad críticas según sea necesario para la biblioteca de marcos en la máquina en la que se ejecuta la aplicación. Usted es responsable de la validación de un extremo a otro del escenario de esta revisión de seguridad.

### <a name="examples"></a>Ejemplos

Sirve para publicar una aplicación independiente. Se creará un archivo ejecutable de macOS de 64 bits.

```dotnet
dotnet publish -r osx-x64
```

Sirve para publicar una aplicación independiente. Se creará un archivo ejecutable de Windows de 64 bits.

```dotnet
dotnet publish -r win-x64
```

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones de .NET Core con la CLI de .NET Core](deploy-with-cli.md)
- [Implementación de aplicaciones de .NET Core con Visual Studio](deploy-with-vs.md)
- [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core.](../rid-catalog.md)
- [Selección de la versión de .NET Core que se va a usar](../versions/selection.md)
