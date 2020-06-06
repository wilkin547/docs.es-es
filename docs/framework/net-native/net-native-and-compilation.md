---
title: .NET Native y compilación
ms.date: 03/30/2017
ms.assetid: e38ae4f3-3e3d-42c3-a4b8-db1aa9d84f85
ms.openlocfilehash: cf5c9f05b2f2cb4ca15e4add5b53bc9bdca757a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128243"
---
# <a name="net-native-and-compilation"></a>.NET Native y compilación

Las aplicaciones de Windows 8.1 y del escritorio de Windows destinadas a.NET Framework se escriben en un lenguaje de programación determinado y se compilan en lenguaje intermedio (IL). En runtime, el compilador Just-In-Time (JIT) es el responsable de compilar el IL en código nativo para la máquina local antes de que un método se ejecute por primera vez. En cambio, la cadena de herramientas de .NET Native convierte código fuente en código nativo en tiempo de compilación. En este tema se compara .NET Native con otras tecnologías de compilación disponibles para las aplicaciones de .NET Framework. Asimismo, también se proporciona información general práctica sobre el modo en que .NET Native genera código nativo que sirve para comprender por qué las excepciones que se producen en el código compilado con .NET Native no se producen en código compilado JIT.

## <a name="net-native-generating-native-binaries"></a>.NET Native: generación de archivos binarios nativos

Una aplicación que está destinada a .NET Framework y no se compila mediante la cadena de herramientas de .NET Native se compone del ensamblado de aplicación, que incluye lo siguiente:

- Los [metadatos](../../standard/metadata-and-self-describing-components.md) que describen el ensamblado, sus dependencias, los tipos que contiene y sus miembros. Los metadatos se usan para la reflexión y acceso en tiempo de ejecución y en algunos casos también por el compilador y las herramientas de compilación.

- Código de implementación Se compone de códigos de operación de lenguaje intermedio (IL). En runtime, el compilador de Just-In-Time (JIT) lo convierte en código nativo para la plataforma de destino.

 Además de su ensamblado de aplicación principal, una aplicación requiere lo siguiente:

- Las bibliotecas de clases adicionales o ensamblados de terceros que requiera su aplicación. De forma similar, estos ensamblados incluyen metadatos que describen el ensamblado, sus tipos y sus miembros, así como el IL que implementa todos los miembros de tipo.

- La biblioteca de clases de .NET Framework. Se trata de una colección de ensamblados que se instala en el sistema local cuando se instala .NET Framework. Los ensamblados de la biblioteca de clases de .NET Framework incluyen un conjunto completo de metadatos y código de implementación.

- Common Language Runtime. Se trata de una colección de bibliotecas de vínculos dinámicos que realizan servicios como la carga de ensamblados, la recolección de elementos no utilizados y la administración de memoria, el control de excepciones, compilación Just-In-Time, comunicación remota e interoperabilidad. Al igual que la biblioteca de clases, el runtime se instala en el sistema local como parte de la instalación de .NET Framework.

Tenga en cuenta que, para que la aplicación se ejecute correctamente, deben estar presentes la totalidad de Common Language Runtime, los metadatos y el lenguaje intermedio de todos los tipos de ensamblados específicos de la aplicación, los ensamblados de terceros y los ensamblados del sistema.

## <a name="net-native-and-just-in-time-compilation"></a>Compilación de .NET Native y Just-In-Time

La entrada de la cadena de herramientas de .NET Native es la aplicación de la Tienda Windows creada por el compilador de C# o de Visual Basic. En otras palabras, la cadena de herramientas de .NET Native empieza a ejecutarse cuando el compilador de lenguaje ha finalizado la compilación de una aplicación de la Tienda Windows.

> [!TIP]
> Dado que la entrada a .NET Native es el IL y los metadatos que se escriben en los ensamblados administrados, puede generar código personalizado u otras operaciones personalizadas mediante eventos anteriores o posteriores a la compilación o modificando el archivo de proyecto de MSBuild.
>
> Sin embargo, no se admiten las categorías de herramientas que modifican el IL y que evitan que la cadena de herramientas de .NET analice una aplicación. Los ofuscadores son las herramientas más importantes de este tipo.

En el proceso de convertir una aplicación de IL a código nativo, la cadena de herramientas de .NET Native realiza operaciones como la siguiente:

- En determinadas rutas de código, reemplaza el código que se basa en la reflexión y los metadatos por código nativo estático. Por ejemplo, si un tipo de valor no reemplaza el método <xref:System.ValueType.Equals%2A?displayProperty=nameWithType>, la prueba predeterminada de igualdad usa la reflexión para recuperar objetos <xref:System.Reflection.FieldInfo> que representan los campos del tipo de valor y, a continuación, compara los valores de campo de dos instancias. Cuando se compila en código nativo, la cadena de herramientas de .NET Native reemplaza el código de reflexión y los metadatos por una comparación estática de los valores de campo.

- Siempre que puede, intenta eliminar todos los metadatos.

- En los ensamblados de la aplicación final solo incluye el código de implementación que se invoca realmente por parte de la aplicación. Esto afecta especialmente al código de bibliotecas de terceros y a la biblioteca de clases de .NET Framework. Como resultado, una aplicación ya no depende de las bibliotecas de terceros ni de la biblioteca de clases completa de .NET Framework; en su lugar, el código de bibliotecas de clases de .NET Framework y de terceros ahora es local a la aplicación.

- Reemplaza el CLR completo con un tiempo de ejecución refactorizado contiene principalmente el recolector de elementos no utilizados. El tiempo de ejecución refactorizado se encuentra en una biblioteca denominada mrt100_app.dll que es local a la aplicación y que solo tiene unos cientos de kilobytes de tamaño. Esto es posible porque la vinculación estática elimina la necesidad de muchos de los servicios realizados por Common Language Runtime.

  > [!NOTE]
  > .NET Native usa el mismo recolector de elementos no utilizados que Common Language Runtime. En el recolector de elementos no utilizados de .NET Native, la recolección en segundo plano está habilitada de forma predeterminada. Para obtener más información sobre la recolección de elementos no utilizados, vea [Fundamentals of Garbage Collection](../../standard/garbage-collection/fundamentals.md) (Conceptos básicos de la recolección de elementos no utilizados).

> [!IMPORTANT]
> .NET Native compila una aplicación completa en una aplicación nativa. No permite compilar un único ensamblado que contiene una biblioteca de clases en código nativo, por lo que se puede llamar de forma independiente desde el código administrado.

La aplicación resultante generada por la cadena de herramientas de .NET Native se escribe en un directorio denominado ilc.out en el directorio Debug o Release del directorio del proyecto. Consta de los siguientes archivos:

- *\<appName>*. exe, un archivo ejecutable de código auxiliar que simplemente transfiere el control a una `Main` exportación especial en *\<appName>* . dll.

- *\<appName>*. dll, una biblioteca de vínculos dinámicos de Windows que contiene todo el código de la aplicación, así como el código de la biblioteca de clases de .NET Framework y cualquier biblioteca de terceros en la que tenga una dependencia.  También contiene el código de soporte, como el código necesario para interactuar con Windows y para serializar objetos en la aplicación.

- mrt100_app.dll, que es un runtime refactorizado que proporciona servicios de runtime como la recolección de elementos no utilizados.

 Todas las dependencias se capturan el manifiesto de la aplicación APPX.  Además de las aplicaciones exe, dll y mrt100_app.dll, empaquetadas directamente en el APPX, se incluyen dos archivos más:

- msvcr140_app.dll, que es la biblioteca de tiempo de ejecución de C (CRT) usada por mrt100_app.dll. Se incluye mediante una referencia de marco en el paquete.

- mrt100.dll. Esta biblioteca incluye funciones que pueden mejorar el rendimiento de mrt100_app.dll, aunque su ausencia no impide el funcionamiento de mrt100_app.dll. Si está presente, se carga desde el directorio system32 en el equipo local.

Dado que la cadena de herramientas de .NET Native vincula el código de implementación en la aplicación, pero solo cuando sabe que su aplicación es la que invoca en realidad ese código, es posible que los metadatos o el código de implementación que son necesarios en los escenarios siguientes no se incluyan con la aplicación:

- Reflexión.

- Invocación dinámica o en tiempo de ejecución.

- Serialización y deserialización.

- Interoperabilidad COM.

Si el código de implementación o los metadatos necesarios no están presentes en runtime, el runtime de .NET Native genera una excepción. Para evitar estas excepciones y asegurarse de que la cadena de herramientas de .NET Native incluye el código de implementación y los metadatos necesarios, use un [archivo de directivas en tiempo de ejecución](runtime-directives-rd-xml-configuration-file-reference.md), que es un archivo XML que designa los elementos del programa cuyo código de implementación o metadatos deben estar disponibles en tiempo de ejecución y les asigna una directiva en tiempo de ejecución. A continuación se incluye el archivo de directivas de runtime predeterminado que se agrega a un proyecto de la Tienda Windows compilado por la cadena de herramientas de .NET Native:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>
```

Esto habilita la reflexión y la invocación dinámica en todos los tipos, así como sus miembros, de todos los ensamblados del paquete de aplicación. Sin embargo, no habilita la reflexión ni la activación dinámica de tipos en ensamblados de biblioteca de clases de .NET Framework. En muchos casos, esto es suficiente.

## <a name="net-native-and-ngen"></a>.NET Native y NGEN

El [generador de imágenes nativas](../tools/ngen-exe-native-image-generator.md) (NGEN) compila los ensamblados en código nativo y los instala en la caché de imágenes nativas del equipo local. Sin embargo, a pesar de que NGEN (al igual que .NET Native) genera código nativo, se diferencia de .NET Native en algunos aspectos importantes:

- Si no hay ninguna imagen nativa disponible para un método concreto, NGEN recurre a aplicar JIT al código. Esto significa que las imágenes nativas deben seguir incluyendo metadatos e IL en caso de que NGEN deba recurrir a la compilación JIT. En cambio, .NET Native solo genera imágenes nativas y no recurre a la compilación JIT. Como resultado, tan solo deben conservarse los metadatos necesarios para algunos escenarios de interoperabilidad, serialización y reflexión.

- NGEN sigue confiando en Common Language Runtime para servicios como la carga de ensamblados, la comunicación remota, la interoperabilidad, la administración de memoria, la recolección de elementos no utilizados y, si es necesario, la compilación JIT. En .NET Native, muchos de estos servicios son innecesarios (la compilación JIT) o se resuelve en tiempo de compilación y se incorporan en el ensamblado de la aplicación. El resto de servicios, de los cuales el más importante es la recolección de elementos no utilizados, se incluyen en un runtime refactorizado mucho más pequeño denominado mrt100_app.dll.

- Las imágenes NGEN suelen ser frágiles. Por ejemplo, si se producen una revisión o un cambio en una dependencia, es necesario aplicar de nuevo NGEN en los ensamblados que la usan. Esto es particularmente cierto con los ensamblados del sistema de la biblioteca de clases de .NET Framework. En cambio, .NET Native permite que las aplicaciones se sirvan de forma independiente.

## <a name="see-also"></a>Consulte también

- [Metadatos y componentes autodescriptivos](../../standard/metadata-and-self-describing-components.md)
- [Buceando en .NET Native (vídeo de Channel 9)](https://channel9.msdn.com/Shows/Going+Deep/Inside-NET-Native)
- [Reflexión y .NET Native](reflection-and-net-native.md)
- [Solución de problemas generales de .NET Native](net-native-general-troubleshooting.md)
