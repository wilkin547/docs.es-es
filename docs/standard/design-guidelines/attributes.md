---
title: Attributes1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c169586091f0e7e094e0231f9e247e8907371ec4
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="attributes"></a>Atributos
<xref:System.Attribute?displayProperty=nameWithType> es una clase base que se utiliza para definir atributos personalizados.  
  
 Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros. Que se almacenan en los metadatos del ensamblado y se pueden tener acceso en tiempo de ejecución mediante las API de reflexión. Por ejemplo, el marco de trabajo define la <xref:System.ObsoleteAttribute>, que pueden aplicarse a un tipo o miembro para indicar que el tipo o miembro está en desuso.  
  
 Atributos pueden tener una o varias propiedades que transportan datos adicionales relacionados con el atributo. Por ejemplo, `ObsoleteAttribute` podría incluir información adicional acerca de la versión en que un tipo o miembro se obtuvo en desuso y la descripción de las nuevas API reemplazando la API obsoleta.  
  
 Algunas propiedades de un atributo deben especificarse cuando se aplica el atributo. Estos se conocen como las propiedades necesarias o argumentos necesarios, ya que se representan como parámetros posicionales constructor. Por ejemplo, el <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de la <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.  
  
 Las propiedades que no necesariamente deben especificarse cuando se aplica el atributo se denominan propiedades opcionales (o argumentos opcionales). Dichas reglas se representan mediante propiedades configurables. Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo. Por ejemplo, el <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> propiedad representa un argumento opcional.  
  
 **✓ HACER** nombres de las clases de atributo personalizado con el sufijo "Atributos".  
  
 **✓ HACER** aplicar el <xref:System.AttributeUsageAttribute> a atributos personalizados.  
  
 **✓ HACER** proporcionar propiedades configurables para los argumentos opcionales.  
  
 **✓ HACER** proporcionan propiedades get-only de argumentos necesarios.  
  
 **✓ HACER** proporcionan parámetros de constructor para inicializar las propiedades que corresponden a los argumentos necesarios. Cada parámetro debe tener el mismo nombre (aunque con distintas mayúsculas y minúsculas) como la propiedad correspondiente.  
  
 **X evitar** proporcionar parámetros del constructor para inicializar las propiedades que corresponden a los argumentos opcionales.  
  
 En otras palabras, no tiene propiedades que se pueden establecer con un constructor y un establecedor. Esta instrucción hace muy explícitas qué argumentos son opcionales y que son necesarios y evita la necesidad de dos maneras de hacer lo mismo.  
  
 **X evitar** sobrecarga de constructores de atributo personalizado.  
  
 Tener solo un constructor claramente comunica con el usuario que los argumentos son obligatorios y cuáles son opcionales.  
  
 **✓ HACER** sellar clases de atributos personalizados, si es posible. Esto acelera la búsqueda para el atributo.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
