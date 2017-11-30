---
title: "Novedades en el estándar de .NET"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>Novedades en el estándar de .NET

El estándar de .NET es una especificación formal que define un conjunto con control de versiones de API que deben estar disponibles en las implementaciones de .NET es compatible con esa versión del estándar. .NET Standard está dirigido a los desarrolladores de bibliotecas. Una biblioteca que tenga como destino una versión estándar de .NET se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.

La versión más reciente de la norma de .NET es 2.0. Se incluye con el SDK de .NET Core 2.0, así como con Visual Studio 2017 versión 15.3 con la carga de trabajo de .NET Core instalado.

## <a name="supported-net-implementations"></a>Implementaciones de .NET compatibles

El estándar de .NET 2.0 es compatible con las siguientes implementaciones. NET:

- Núcleo de .NET 2.0
- .NET Framework 4.6.1
- Mono 5.4.
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- Plataforma universal de Windows 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>Novedades en el estándar de .NET 2.0
 
El estándar de .NET 2.0 incluye las siguientes características nuevas:

**Un conjunto de API ampliamente expandido**

A través de la versión 1.6, el estándar de .NET incluyen un subconjunto relativamente pequeño de API. Entre los que quedan excluidos estaban muchas API que se utilizan con frecuencia en .NET Framework o Xamarin. Esto complica desarrollo, ya que requiere que los desarrolladores encuentran sustitutos adecuados para las API familiarizadas cuando desarrollan aplicaciones y bibliotecas destinadas a varias implementaciones. NET. El estándar de .NET 2.0 aborda esta limitación mediante la adición de más de 20.000 API más que estaban disponibles en .NET estándar 1.6, la versión anterior del estándar. Para obtener una lista de las API que se han agregado para el estándar de .NET 2.0, consulte [.NET 2.0 estándar vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Algunas de las adiciones a la <xref:System> incluir el espacio de nombres estándar de .NET 2.0:

- Compatibilidad con la <xref:System.AppDomain> clase.
- Mejor compatibilidad para trabajar con matrices de miembros adicionales en la <xref:System.Array> clase.
- Mejor compatibilidad para trabajar con atributos de miembros adicionales en la <xref:System.Attribute> clase.
- Calendario mejor compatibilidad con y opciones de formato adicionales para <xref:System.DateTime> valores.
- Adicionales <xref:System.Decimal> funcionalidad de redondeo.
- Funcionalidad adicional en la <xref:System.Environment> clase.
- Mejorado control sobre el recolector de elementos no utilizados a través de la <xref:System.GC> clase.
- Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en el <xref:System.String> clase.
- Soporte técnico para el horario de verano ajustes y tiempos de transición en el <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime> clases.
- Mejoran significativamente la funcionalidad en el <xref:System.Type> clase.
- Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext> parámetros.

**Compatibilidad con bibliotecas de .NET Framework**

La gran mayoría de las bibliotecas de tener como destino el .NET Framework en lugar de .NET estándar. Sin embargo, la mayoría de las llamadas de esas bibliotecas es para las API que se incluyen en el estándar de .NET 2.0. A partir de .NET estándar 2.0, se pueden tener acceso a las bibliotecas de .NET Framework de una biblioteca estándar de .NET mediante el uso de un [schim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification). Este nivel de compatibilidad es transparente para los desarrolladores; no tienes que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.

El único requisito es que las API que se llama a la biblioteca de clases de .NET Framework deben incluirse en el estándar de .NET 2.0.

**Compatibilidad con Visual Basic**

Ahora puede desarrollar bibliotecas estándar de .NET en Visual Basic. Para los desarrolladores de Visual Basic mediante Visual Studio 2017 versión 15.3 o posterior con la carga de trabajo de .NET Core instalado, Visual Studio ahora incluye una plantilla de biblioteca de clases de .NET estándar. Para los desarrolladores de Visual Basic que utilizan otras herramientas de desarrollo y los entornos, puede usar el [dotnet nueva](../../core/tools/dotnet-new.md) comando para crear un proyecto de biblioteca de .NET estándar. Para obtener más información, consulte el [compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling).

<a name="tooling" />**Compatibilidad con herramientas de bibliotecas estándar de .NET**

Con la versión de .NET Core 2.0 y .NET 2.0 estándar, tanto Visual Studio de 2017 y [.NET Core interfaz de línea de comandos (CLI)](../../core/tools/index.md) incluyen compatibilidad con herramientas de creación de bibliotecas de .NET estándar. 

Si instala Visual Studio con la **.NET Core el desarrollo multiplataforma** carga de trabajo, puede crear un proyecto de biblioteca estándar de .NET 2.0 mediante el uso de una plantilla de proyecto, como se muestra en la ilustración siguiente. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Agregar proyecto de biblioteca nuevo estándar de .NET](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Agregar proyecto de biblioteca nuevo estándar de .NET](./media/std-project-vb.png)
---

Si está usando la CLI de .NET Core, el siguiente [dotnet nueva](../../core/tools/dotnet-new.md) comando crea un proyecto de biblioteca de clases que tenga como destino el estándar de .NET 2.0.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>Vea también
[Estándar de .NET](../net-standard.md)
[presentación estándar de .NET](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
