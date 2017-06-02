---
title: "Dise&#241;o de propiedades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "instrucciones de diseño de miembros, propiedades"
  - "propiedades [.NET Framework], instrucciones de diseño"
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dise&#241;o de propiedades
Aunque las propiedades son técnicamente muy similares a los métodos, son bastante diferentes en cuanto a sus escenarios de uso. Deben considerarse como campos inteligentes. Tienen la sintaxis de llamada de campos y la flexibilidad de los métodos.  
  
 **✓ hacer** crear propiedades get\-only si el llamador no debería poder cambiar el valor de la propiedad.  
  
 Tenga en cuenta que, si el tipo de la propiedad es un tipo de referencia mutable, el valor de propiedad se puede cambiar incluso si la propiedad es get\-only.  
  
 **X no** proporcionar sólo conjunto de propiedades o el establecedor de accesibilidad más amplio que el captador.  
  
 Por ejemplo, no utilice propiedades con un establecedor público y un captador protegido.  
  
 Si no se puede proporcionar el captador de propiedad, implementar la funcionalidad como un método en su lugar. Considere la posibilidad de iniciar el nombre del método con `Set` y seguir con lo que habría denominado la propiedad. Por ejemplo, <xref:System.AppDomain> tiene un método llamado `SetCachePath` en lugar de tener una propiedad de sólo establecimiento denominada `CachePath`.  
  
 **✓ hacer** proporcionar valores predeterminados razonables para todas las propiedades, garantizando que los valores predeterminados no producen una vulnerabilidad de seguridad o código terriblemente ineficaz.  
  
 **✓ hacer** permiten que las propiedades que puede establecer en cualquier orden, incluso si el resultado es un estado temporal no válido del objeto.  
  
 Es común para dos o más propiedades que se interrelacionan a un punto donde algunos valores de una propiedad pueden no ser válidos, dados los valores de otras propiedades en el mismo objeto. En tales casos, deben posponerse excepciones resultantes de un estado no válido hasta que las propiedades interrelacionadas realmente se utilizan conjuntamente por el objeto.  
  
 **✓ hacer** conserve el valor anterior si un establecedor de propiedad inicia una excepción.  
  
 **Evitar X** iniciar excepciones desde los captadores de propiedades.  
  
 Captadores de propiedades deberían ser operaciones simples y no deben tener las condiciones previas. Si un captador puede producir una excepción, probablemente se debería rediseñar para ser un método. Observe que esta regla no se aplica a los indizadores, que esperamos que las excepciones como resultado de la validación de los argumentos.  
  
### Diseño de propiedades indizadas  
 Una propiedad indizada es una propiedad especial que puede tener parámetros y se puede llamar con una sintaxis especial similar a la indización de matrices.  
  
 Propiedades indizadas se conocen normalmente como indizadores. Los indizadores deben usarse sólo en las API que proporcionan acceso a los elementos de una colección lógica. Por ejemplo, una cadena es un conjunto de caracteres y el indizador en <xref:System.String?displayProperty=fullName> se agregó para tener acceso a los caracteres.  
  
 **✓, considere la posibilidad de** mediante indizadores para proporcionar acceso a los datos almacenados en una matriz interna.  
  
 **✓ considere** proporcionar indizadores en los tipos que representan colecciones de elementos.  
  
 **Evitar X** utilizando propiedades con más de un parámetro indizadas.  
  
 Si el diseño requiere varios parámetros, reconsidere si la propiedad representa realmente un descriptor de acceso a una colección lógica. Si no es así, utilice métodos en su lugar. Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.  
  
 **Evitar X** indizadores con tipos de parámetro distinto de <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.String?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, o una enumeración.  
  
 Si el diseño requiere otros tipos de parámetros, fuertemente vuelva a evaluar si la API realmente representa un descriptor de acceso a una colección lógica. Si no es así, utilice un método. Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.  
  
 **✓ hacer** utilizar el nombre `Item` para propiedades indizadas a menos que haya nombre obviamente mejor \(por ejemplo, consulte el <xref:System.String.Chars%2A> propiedad `System.String`\).  
  
 En C\#, los indizadores son de forma predeterminada con el nombre de elemento. La <xref:System.Runtime.CompilerServices.IndexerNameAttribute> puede utilizarse para personalizar este nombre.  
  
 **X no** proporcionan un indizador y métodos que son semánticamente equivalentes.  
  
 **X no** proporcionar más de una familia de indizadores sobrecargados en un tipo.  
  
 Esto se aplica por el compilador de C\#.  
  
 **X no** no predeterminados de uso de propiedades indizan.  
  
 Esto se aplica por el compilador de C\#.  
  
### Eventos de notificación de cambio de propiedad  
 A veces resulta útil para proporcionar un evento de notificación al usuario de los cambios en un valor de propiedad. Por ejemplo, `System.Windows.Forms.Control` provoca un `TextChanged` evento después del valor de su `Text` propiedad ha cambiado.  
  
 **✓ considere** generar cambiar eventos de notificación cuando se modifican los valores de propiedad en la API de alto nivel \(normalmente componentes de diseñador\).  
  
 Si hay un caso apropiado para un usuario saber cuando cambia una propiedad de un objeto, el objeto debe generar un evento de notificación de cambio de la propiedad.  
  
 Sin embargo, es probable que merece la pena la sobrecarga para provocar estos eventos para la API de bajo nivel como tipos base o colecciones. Por ejemplo, <xref:System.Collections.Generic.List%601> no generaría dichos eventos cuando se agrega un nuevo elemento a la lista y `Count` cambios de propiedad.  
  
 **✓ considere** generar cambiar eventos de notificación cuando cambia el valor de una propiedad a través de fuerzas externas.  
  
 Si cambia un valor de propiedad a través de algún factor externo \(de manera distinta llamando a métodos en el objeto\), generar eventos indican al programador que el valor está cambiando y ha cambiado. Un buen ejemplo es la `Text` propiedad de un control de cuadro de texto. Cuando el usuario escribe texto en un `TextBox`, cambia automáticamente el valor de propiedad.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)