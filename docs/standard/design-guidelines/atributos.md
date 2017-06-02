---
title: "Attributes1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "atributos [.NET Framework], acerca de"
  - "instrucciones de diseño clases biblioteca [.NET Framework], atributos"
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Atributos
<xref:System.Attribute?displayProperty=fullName> es una clase base que se utiliza para definir atributos personalizados.  
  
 Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros. Que se almacenan en los metadatos del ensamblado y se pueden tener acceso en tiempo de ejecución mediante las API de reflexión. Por ejemplo, el marco de trabajo define la <xref:System.ObsoleteAttribute>, que pueden aplicarse a un tipo o miembro para indicar que el tipo o miembro está desusado.  
  
 Atributos pueden tener una o más propiedades que transportan datos adicionales relacionados con el atributo. Por ejemplo, `ObsoleteAttribute` podría incluir información adicional acerca de la versión en que un tipo o miembro tiene desusado y la descripción de las nuevas API reemplazando la API obsoleta.  
  
 Algunas propiedades de un atributo deben especificarse cuando se aplica el atributo. Estos se conocen como las propiedades necesarias o argumentos necesarios, ya que se representan como parámetros del constructor posicionales. Por ejemplo, el <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de la <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.  
  
 Las propiedades que no necesariamente deben especificarse cuando se aplica el atributo se denominan propiedades opcionales \(o argumentos opcionales\). Se representan como propiedades configurables. Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo. Por ejemplo, el <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=fullName> propiedad representa un argumento opcional.  
  
 **✓ hacer** nombres de las clases de atributo personalizado con el sufijo "Atributos".  
  
 **✓ hacer** aplicar el <xref:System.AttributeUsageAttribute> a los atributos personalizados.  
  
 **✓ hacer** proporcionan propiedades configurables para los argumentos opcionales.  
  
 **✓ hacer** proporcionan propiedades get\-only de argumentos necesarios.  
  
 **✓ hacer** proporcionar parámetros de constructor para inicializar las propiedades que corresponden a los argumentos necesarios. Cada parámetro debe tener el mismo nombre \(aunque con distinguen mayúsculas de minúsculas\) como la propiedad correspondiente.  
  
 **Evitar X** proporcionando los parámetros del constructor para inicializar las propiedades que corresponden a los argumentos opcionales.  
  
 En otras palabras, no tiene propiedades que se pueden establecer con un constructor y un establecedor. Esta instrucción hace muy explícito que los argumentos son opcionales y que son necesarias y evita la necesidad de dos maneras de hacer lo mismo.  
  
 **Evitar X** sobrecarga de los constructores de atributo personalizado.  
  
 Tener solo un constructor claramente comunica al usuario los argumentos que son necesarios y que son opcionales.  
  
 **✓ hacer** sellar clases de atributos personalizados, si es posible. Esto acelera la búsqueda para el atributo.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)