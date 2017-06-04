---
title: "Sellar | Microsoft Docs"
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
  - "limitar la extensibilidad"
  - "sellado de clases [.NET Framework]"
  - "evitar la personalización"
  - "clases selladas"
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Sellar
Una de las características de los marcos de trabajo orientados a objetos es que los desarrolladores pueden ampliar y personalizar en formas no anticipados por los diseñadores de framework. Se trata de la eficacia y el riesgo de diseño extensible. Al diseñar su marco, por lo tanto, muy importante diseñar cuidadosamente para extensibilidad cuando se desee y para limitar la extensibilidad cuando es peligroso.  
  
 Un mecanismo eficaz que impide la extensibilidad de sellado. También puede proteger el clases o miembros individuales. Sellar una clase, evita que los usuarios heredan de la clase. Sellado de un miembro, impide que los usuarios invalidar a un miembro determinado.  
  
 **X no** sellar clases sin tener una buena razón para hacerlo.  
  
 Sellar una clase porque no se le ocurre un escenario de extensibilidad no es una buena razón. Los usuarios de Framework desea heredar de clases por diversas razones ocultos, como agregar miembros de comodidad. Consulte [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md) para obtener ejemplos de motivos ocultos los usuarios desean heredar de un tipo.  
  
 Buenas razones para sellar una clase son los siguientes:  
  
-   La clase es una clase estática. Vea [Diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La clase almacena información confidencial de seguridad en miembros protegidos heredados.  
  
-   La clase hereda a muchos miembros virtuales y el costo del sellado de forma individual superaría con creces las ventajas de la clase sellados.  
  
-   La clase es un atributo que requiere la búsqueda en tiempo de ejecución muy rápido. Atributos sellados tienen niveles de rendimiento ligeramente superiores que no sellado. Vea [Atributos](../../../docs/standard/design-guidelines/atributos.md).  
  
 **X no** declarar miembros protegidos o virtuales en tipos sealed.  
  
 Por definición, los tipos sellados no se puede heredar desde. Esto significa que no se puede llamar a los miembros protegidos en tipos sealed, y no se puede invalidar los métodos virtuales en tipos sealed.  
  
 **✓ considere** sellar los miembros reemplazados.  
  
 Problemas que pueden derivarse de presentación de los miembros virtuales \(descritos en [Miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)\) se aplican a invalidaciones, aunque en un grado ligeramente menor. Sellar una invalidación intercepta estos problemas a partir de ese punto en la jerarquía de herencia.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)