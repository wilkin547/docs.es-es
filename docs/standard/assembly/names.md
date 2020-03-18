---
title: Nombres de ensamblado
ms.date: 08/19/2019
helpviewer_keywords:
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
ms.openlocfilehash: 7a1a4d2512ebb002a3153fe2d51f47157136744d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73733100"
---
# <a name="assembly-names"></a>Nombres de ensamblado
Un nombre de ensamblado se almacena en los metadatos y tiene un importante impacto en el ámbito del ensamblado y en su uso por parte de una aplicación. Un ensamblado con nombre seguro tiene un nombre completo que incluye nombre, referencia cultural, clave pública y número de versión. Se conoce como el nombre para mostrar y en los ensamblados cargados puede obtenerse mediante la propiedad <xref:System.Reflection.Assembly.FullName%2A>.

 El runtime usa esta información para buscar el ensamblado y distinguirlo de otros ensamblados con el mismo nombre. Por ejemplo, un ensamblado con nombre seguro llamado `myTypes` podría tener el siguiente nombre completo:

```
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil
```

> [!NOTE]
> La arquitectura del procesador se ha agregado a la identidad del ensamblado en la versión 2.0 de .NET Framework para permitir versiones específicas de procesador de ensamblados. Puede crear versiones de un ensamblado cuya identidad solo se diferencie por la arquitectura del procesador, por ejemplo versiones específicas del procesador de 32 y 64 bits. La arquitectura del procesador no es necesaria para los nombres seguros. Para obtener más información, vea <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>.

 En este ejemplo, el nombre completo indica que el ensamblado `myTypes` tiene un nombre seguro con un token de clave pública, tiene el valor de referencia cultural de inglés de los Estados Unidos y tiene un número de versión de 1.0.1234.0. Su arquitectura del procesador es "msil", lo que significa que será compilado JIT (just-in-time) para código de 32 o 64 bits según el sistema operativo y el procesador.

 El código que solicite tipos en un ensamblado debe usar un nombre completo de ensamblado. Esto se denomina enlace completo. No se permite el enlace parcial, que especifica solo un nombre de ensamblado, al hacer referencia a ensamblados de .NET Framework.

 Todas las referencias a los ensamblados que componen .NET Framework también deben contener el nombre completo del ensamblado. Por ejemplo, una referencia al ensamblado System.Data de .NET Framework para la versión 1.0 incluiría:

```
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089
```

 Tenga en cuenta que la versión corresponde al número de versión de todos los ensamblados de .NET Framework incluidos con la versión 1.0 de .NET Framework. En el caso de los ensamblados de .NET Framework, el valor de la referencia cultural siempre es neutro y la clave pública es la misma que se muestra en el ejemplo anterior.

 Por ejemplo, para agregar una referencia de ensamblado en un archivo de configuración para configurar un agente de escucha de seguimiento, se incluiría el nombre completo del ensamblado de .NET Framework del sistema:

```xml
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />
```

> [!NOTE]
> El runtime trata los nombres de ensamblado sin distinción entre mayúsculas y minúsculas al enlazar a un ensamblado, pero conserva las minúsculas y mayúsculas que se usan en un nombre de ensamblado. Varias herramientas de Windows SDK controlan los nombres de ensamblado sin distinción entre mayúsculas y minúsculas. Para obtener mejores resultados, administre los nombres de ensamblado con distinción entre mayúsculas y minúsculas.

## <a name="name-application-components"></a>Componentes de la aplicación de nombre
 El runtime no tiene en cuenta el nombre de archivo a la hora de determinar la identidad de un ensamblado. La identidad del ensamblado, que se compone del nombre del ensamblado, la versión, la referencia cultural y el nombre seguro, debe ser clara para el runtime.

 Por ejemplo, si tiene un ensamblado denominado *myAssembly.exe* que hace referencia a un ensamblado llamado *myAssembly.dll*, el enlace se produce correctamente si ejecuta *myAssembly.exe*. Sin embargo, si otra aplicación ejecuta *myAssembly.exe* con el método <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType>, el entorno de ejecución determina que `myAssembly` ya se ha cargado cuando *myAssembly.exe* solicita enlazar a `myAssembly`. En este caso, *myAssembly.dll* no se carga nunca. Como *myAssembly.exe* no contiene el tipo solicitado, se produce una excepción <xref:System.TypeLoadException>.

 Para evitar este problema, asegúrese de que los ensamblados que componen la aplicación no tengan el mismo nombre de ensamblado o coloque aquellos con el mismo nombre en directorios distintos.

> [!NOTE]
> En .NET Framework, si coloca un ensamblado con nombre seguro en la caché global de ensamblados, el nombre de archivo del ensamblado debe coincidir con el nombre del ensamblado (sin incluir la extensión del nombre de archivo, como *.exe* o *.dll*). Por ejemplo, si el nombre de archivo de un ensamblado es *myAssembly.dll*, el nombre del ensamblado debe ser `myAssembly`. Los ensamblados privados implementados solamente en el directorio de la aplicación raíz pueden tener un nombre de ensamblado diferente al nombre de archivo.

## <a name="see-also"></a>Vea también

- [Cómo: Determinar el nombre completo de un ensamblado](find-fully-qualified-name.md)
- [Creación de ensamblados](create.md)
- [Ensamblados con nombre seguro](strong-named.md)
- [Caché global de ensamblados](../../framework/app-domains/gac.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md)
