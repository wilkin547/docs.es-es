---
title: Atributos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 12a67d75a5f9642408cca69b2e3764a67f101549
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280587"
---
# <a name="attributes"></a>Atributos

<xref:System.Attribute?displayProperty=nameWithType>es una clase base que se usa para definir atributos personalizados.

 Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros. Se almacenan en los metadatos del ensamblado y se puede tener acceso a ellos en tiempo de ejecución mediante las API de reflexión. Por ejemplo, .NET define el <xref:System.ObsoleteAttribute> atributo, que se puede aplicar a un tipo o un miembro para indicar que el tipo o miembro está en desuso.

 Los atributos pueden tener una o varias propiedades que contienen datos adicionales relacionados con el atributo. Por ejemplo, `ObsoleteAttribute` podría incluir información adicional sobre la versión en la que un tipo o un miembro quedó en desuso y una descripción de la nueva API que reemplaza a la API obsoleta.

 Se deben especificar algunas propiedades de un atributo cuando se aplica el atributo. Estas se conocen como las propiedades requeridas o los argumentos necesarios, porque se representan como parámetros de constructor posicional. Por ejemplo, la <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.

 Las propiedades que no tienen que especificarse necesariamente cuando se aplica el atributo se denominan propiedades opcionales (o argumentos opcionales). Se representan mediante propiedades que se pueden establecer. Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo. Por ejemplo, la <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> propiedad representa un argumento opcional.

 ✔️ Asigne un nombre a las clases de atributos personalizados con el sufijo "Attribute".

 ✔️ Aplique a los <xref:System.AttributeUsageAttribute> atributos personalizados.

 ✔️ proporcionan propiedades que se pueden establecer para los argumentos opcionales.

 ✔️ proporcionan propiedades Get-Only para los argumentos requeridos.

 ✔️ proporcionan parámetros de constructor para inicializar las propiedades correspondientes a los argumentos necesarios. Cada parámetro debe tener el mismo nombre (aunque con distintas mayúsculas y minúsculas) que la propiedad correspondiente.

 ❌Evite proporcionar parámetros de constructor para inicializar las propiedades correspondientes a los argumentos opcionales.

 En otras palabras, no tiene propiedades que se puedan establecer con un constructor y un establecedor. Esta instrucción hace que sea muy explícito qué argumentos son opcionales y cuáles son necesarios, y evita tener dos maneras de hacer lo mismo.

 ❌Evite sobrecargar los constructores de atributos personalizados.

 Tener un solo constructor se comunica claramente al usuario qué argumentos son obligatorios y cuáles son opcionales.

 ✔️ DEBE sellar las clases de atributos personalizados, si es posible. Esto hace que la búsqueda del atributo sea más rápida.

 *Partes &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de uso](usage-guidelines.md)
