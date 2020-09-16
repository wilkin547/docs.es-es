---
title: Introducción a .NET Native
ms.date: 03/30/2017
ms.assetid: fc9e04e8-2d05-4870-8cd6-5bd276814afc
ms.openlocfilehash: b6cd4acaa377de7fc172fb12c9fb9ff1b832f88a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551215"
---
# <a name="getting-started-with-net-native"></a>Introducción a .NET Native

El conjunto de procedimientos que se debe seguir es el mismo, independientemente de si está creando una nueva aplicación de Windows para Windows 10 o si está migrando una aplicación que ya existe en la Tienda Windows. Para crear una aplicación .NET Native, siga estos pasos:

1. [Desarrolle una aplicación de plataforma universal de Windows (UWP) destinada a Windows 10](#Step1)y pruebe la aplicación para asegurarse de que funciona correctamente.

2. [Administre el uso de reflexión y serialización adicionales](#Step2).

3. [Implemente y pruebe las compilaciones de lanzamiento de la aplicación](#Step3).

4. [Resuelva manualmente los metadatos que faltan](#Step4) y repita el [paso 3](#Step3) hasta que todos los problemas estén solucionados.

> [!NOTE]
> Si va a migrar una aplicación de la tienda Windows existente a .NET Native, asegúrese de revisar [la migración de la aplicación de la tienda Windows a .net Native](migrating-your-windows-store-app-to-net-native.md).

<a name="Step1"></a>

## <a name="step-1-develop-and-test-debug-builds-of-your-uwp-app"></a>Paso 1: desarrollar y probar compilaciones de depuración de la aplicación de UWP

Tanto si va a desarrollar una nueva aplicación o migrar una ya existente, el procedimiento es el mismo para cualquier aplicación de Windows.

1. Crear un nuevo proyecto de UWP en Visual Studio mediante la plantilla de aplicación universal de Windows para Visual C# o Visual Basic. De forma predeterminada, todas las aplicaciones de UWP tienen como destino CoreCLR y sus versiones de lanzamiento se compilan con la cadena de herramientas de .NET Native.

2. Tenga en cuenta que existen algunos problemas de compatibilidad conocidos entre la compilación de proyectos de aplicaciones de UWP con la cadena de herramientas de .NET Native y sin ella. Consulte la [guía de migración](migrating-your-windows-store-app-to-net-native.md) para más información.

Ahora puede escribir código de C# o Visual Basic en el área expuesta .NET Native que se ejecuta en el sistema local (o en el simulador).

> [!IMPORTANT]
> A medida que vaya desarrollando la aplicación, anote cualquier uso de serialización o reflexión en el código.

De forma predeterminada, las compilaciones de depuración se compilan JIT para habilitar la implementación rápida de F5, mientras que las compilaciones de versión se compilan mediante la tecnología de precompilación .NET Native. Esto significa que debe compilar y probar las compilaciones de depuración de la aplicación para asegurarse de que funcionan normalmente antes de compilarlas con la cadena de herramientas de .NET Native.

<a name="Step2"></a>

## <a name="step-2-handle-additional-reflection-and-serialization-usage"></a>Paso 2: Administrar el uso de reflexión y serialización adicionales

Se agrega de forma automática un archivo de directivas en tiempo de ejecución, Default.rd.xml, al proyecto cuando lo crea. Si desarrolla en C#, se encuentra en la carpeta **Propiedades** de su proyecto. Si desarrolla en Visual Basic, se encuentra en la carpeta **Mi proyecto** de su proyecto.

> [!NOTE]
> Para obtener información general acerca del proceso de compilación de .NET Native que proporciona información general sobre por qué se necesita un archivo de directivas en tiempo de ejecución, consulte [.NET Native y compilación](net-native-and-compilation.md).

El archivo de directivas en tiempo de ejecución se usa para definir los metadatos que necesita la aplicación en tiempo de ejecución. En algunos casos, la versión predeterminada del archivo puede ser adecuada. Sin embargo, es posible que algunos códigos que se basan en la serialización o la reflexión requieran entradas adicionales en el archivo de directivas en tiempo de ejecución.

**Serialización**

Existen dos categorías de serializadores y ambas pueden requerir entradas extra en el archivo de directivas en tiempo de ejecución:

- Serializadores no basados en la reflexión. Los serializadores de la biblioteca de clases .NET Framework, como las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer> , no usan reflexión. Sin embargo, requieren que el código se genere en función del objeto que se va a serializar o deserializar.  Para más información, consulte la sección "Serializadores de Microsoft" en [Serialization and Metadata](serialization-and-metadata.md).

- Serializadores de terceros. Las bibliotecas de serialización de terceros, la más común de las cuales es el serializador JSON Newtonsoft, suelen basarse en la reflexión y requieren entradas en el \* archivo.rd.xml para admitir la serialización y deserialización de objetos. Para más información, vea la sección "Serializadores de terceros" en [Serialization and Metadata](serialization-and-metadata.md).

**Métodos basados en la reflexión**

En algunos casos, el uso de reflexión en el código no es obvio. Algunas API comunes o patrones de programación no se consideran parte de la API de reflexión, pero se basan en la reflexión para ejecutarse correctamente. Esto incluye los siguientes métodos de creación de instancias de tipo y de construcción de métodos:

- El método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>

- Los métodos <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> y <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>

- El método <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> .

Para obtener más información, consulta [APIs That Rely on Reflection](apis-that-rely-on-reflection.md).

> [!NOTE]
> Los nombres de tipo que se usan en los archivos de directivas en tiempo de ejecución deben ser nombres completos. Por ejemplo, el archivo debe mostrar "System.String" en lugar de "String".

<a name="Step3"></a>

## <a name="step-3-deploy-and-test-the-release-builds-of-your-app"></a>Paso 3: implementar y probar las compilaciones de lanzamiento de la aplicación

Después de actualizar el archivo de directivas en tiempo de ejecución, puede recompilar e implementar compilaciones de depuración de la aplicación. Los archivos binarios de .NET Native se colocan en el subdirectorio ILC. out del directorio especificado en el cuadro de texto **ruta de acceso** de los resultados de compilación del cuadro de diálogo **propiedades** del proyecto, pestaña **compilar** . Los archivos binarios que no están en esta carpeta no se han compilado con .NET Native. Pruebe la aplicación exhaustivamente y pruebe todos los escenarios, incluidos los escenarios de error, en cada una de las plataformas de destino.

Si la aplicación no funciona correctamente (en especial, en los casos donde se generen excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md) o [MissingInteropDataException](missinginteropdataexception-class-net-native.md) en tiempo de ejecución), siga las instrucciones de la siguiente sección, [Paso 4: Resolver manualmente los metadatos que faltan](#Step4). Habilitar las primeras excepciones puede ayudarle a encontrar estos errores.

Cuando haya probado y depurado las compilaciones de depuración de la aplicación y esté seguro de que ha eliminado las excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md) y [MissingInteropDataException](missinginteropdataexception-class-net-native.md) , debe probar la aplicación como una aplicación optimizada de .net Native. Para ello, cambie la configuración del proyecto activo de **Depurar** a **Liberar**.

<a name="Step4"></a>

## <a name="step-4-manually-resolve-missing-metadata"></a>Paso 4: Resolver manualmente los metadatos que faltan

El error más común que encontrará con .NET Native que no encuentre en el escritorio es una excepción de tiempo de ejecución [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)o [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) . En algunos casos, la ausencia de metadatos se puede manifestar en un comportamiento impredecible o, incluso, en errores de la aplicación. En esta sección se describe cómo puede depurar y resolver estas excepciones agregando directivas al archivo de directivas en tiempo de ejecución. Para obtener información sobre el formato de las directivas de tiempo de ejecución, vea [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md). Tras agregar las directivas en tiempo de ejecución, debe [implementar y volver a probar la aplicación](#Step3) y resolver cualquier excepción [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)o  [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) hasta que no se generen más excepciones.

> [!TIP]
> Especifique las directivas en tiempo de ejecución en un nivel elevado para que la aplicación sea resistente a los cambios de código.  Recomendamos agregar directivas en tiempo de ejecución en los niveles de espacio de nombres y de tipo, en lugar de hacerlo en el nivel de miembro. Tenga en cuenta que puede haber una compensación entre la resistencia y los archivos con tiempos de compilación más prolongados.

Considere las siguientes cuestiones si se trata de una excepción de metadatos que faltan:

- ¿Qué intentaba hacer la aplicación antes de la excepción?

  - Por ejemplo, ¿enlazaba datos, serializaba o deserializaba datos o usaba directamente la API de reflexión?

- ¿Se trata de un caso aislado o cree que surgirá el mismo problema con otros tipos?

  - Por ejemplo, se genera una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) al serializar un tipo en el modelo de objetos de la aplicación.  Si sabe de otros tipos que se van a serializar, puede agregar también directivas en tiempo de ejecución para esos tipos (o para sus espacios de nombres contenedores, dependiendo de cómo esté organizado el código).

- ¿Puede volver a escribir el código para que no haga uso de la reflexión?

  - Por ejemplo, ¿utiliza el código la palabra clave `dynamic` cuando se sabe qué tipo esperar?

  - ¿Llama el código a un método que depende de la reflexión cuando existe una alternativa mejor?

> [!NOTE]
> Para obtener más información sobre cómo controlar los problemas derivados de las diferencias en la reflexión y la disponibilidad de los metadatos en aplicaciones de escritorio y .NET Native, consulte [API que dependen de la reflexión](apis-that-rely-on-reflection.md).

Si desea ver algunos ejemplos específicos de control de excepciones y otros problemas que se producen al probar la aplicación, consulte:

- [Ejemplo: control de excepciones al enlazar datos](example-handling-exceptions-when-binding-data.md)

- [Ejemplo: solucionar problemas de programación dinámica](example-troubleshooting-dynamic-programming.md)

- [Excepciones de tiempo de ejecución en las aplicaciones nativas de .NET](runtime-exceptions-in-net-native-apps.md)

## <a name="see-also"></a>Vea también

- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Instalación y configuración de .NET Native](/previous-versions/dn600164(v=vs.110))
- [.NET Native y compilación](net-native-and-compilation.md)
- [Reflexión y .NET Native](reflection-and-net-native.md)
- [API basada en la reflexión](apis-that-rely-on-reflection.md)
- [Serialización y metadatos](serialization-and-metadata.md)
- [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md)
