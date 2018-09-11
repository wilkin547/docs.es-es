---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259511"
---
# <a name="attributes"></a>Atributos
<xref:System.Attribute?displayProperty=nameWithType> se utiliza una clase base para definir atributos personalizados.  
  
 Los atributos son anotaciones que pueden agregarse a elementos de programación como ensamblados, tipos, miembros y parámetros. Que se almacenan en los metadatos del ensamblado y se pueden tener acceso en tiempo de ejecución mediante las API de reflexión. Por ejemplo, el marco de trabajo define el <xref:System.ObsoleteAttribute>, que pueden aplicarse a un tipo o miembro para indicar que el tipo o miembro en desuso.  
  
 Los atributos pueden tener una o varias propiedades que transportan datos adicionales relacionados con el atributo. Por ejemplo, `ObsoleteAttribute` podría incluir información adicional sobre la versión en que un tipo o miembro se obtuvo en desuso y la descripción de las nuevas API reemplazando la API obsoleta.  
  
 Algunas propiedades de un atributo se deben especificar cuando se aplica el atributo. Estos se conocen como las propiedades necesarias o los argumentos necesarios, ya que se representan como parámetros de constructor posicional. Por ejemplo, el <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de la <xref:System.Diagnostics.ConditionalAttribute> es una propiedad necesaria.  
  
 Las propiedades que no necesariamente deben especificarse cuando se aplica el atributo se denominan propiedades opcionales (o argumentos opcionales). Se representan mediante las propiedades configurables. Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo. Por ejemplo, el <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> propiedad representa un argumento opcional.  
  
 **✓ DO** nombres de las clases de atributo personalizado con el sufijo "Atributos".  
  
 **✓ DO** aplicar el <xref:System.AttributeUsageAttribute> a atributos personalizados.  
  
 **✓ DO** proporcionar propiedades configurables para los argumentos opcionales.  
  
 **✓ DO** proporcionan propiedades get-only de argumentos necesarios.  
  
 **✓ DO** proporcionan parámetros de constructor para inicializar las propiedades que corresponden a los argumentos necesarios. Cada parámetro debe tener el mismo nombre (aunque con distinguen mayúsculas de minúsculas) como la propiedad correspondiente.  
  
 **X AVOID** proporcionar parámetros del constructor para inicializar las propiedades que corresponden a los argumentos opcionales.  
  
 En otras palabras, no tiene propiedades que se pueden establecer con un constructor y un establecedor. Esta instrucción hace que sea muy explícito que los argumentos son opcionales y que son necesarias y evita tener dos formas de hacer lo mismo.  
  
 **X AVOID** sobrecarga de constructores de atributo personalizado.  
  
 Tener solo un constructor claramente comunica al usuario qué argumentos son obligatorios y cuáles son opcionales.  
  
 **✓ DO** sellar clases de atributos personalizados, si es posible. Esto hace que la búsqueda para el atributo con mayor rapidez.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
