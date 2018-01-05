---
title: Nombres de miembros de tipos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d489d4cf61adfe8550bd16b85cd658e0d545c861
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-type-members"></a>Nombres de miembros de tipos
Se realizan los tipos de miembros: métodos, propiedades, eventos, constructores y campos. Las siguientes secciones describen las directrices para asignar nombres a los miembros de tipo.  
  
## <a name="names-of-methods"></a>Nombres de métodos  
 Porque los métodos son el medio de una acción, las instrucciones de diseño requieren que los nombres de método sea verbos o sintagmas verbales. Sigue esta directriz también sirve para distinguir los nombres de método de propiedad y nombres de tipos, que son frases sustantivo o adjetivo.  
  
 **✓ HACER** proporcione nombres de métodos que son verbos o sintagmas verbales.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Nombres de propiedades  
 A diferencia de otros miembros, propiedades deberían contar con nombres adjetivo o frase. Eso es porque una propiedad hace referencia a los datos y el nombre de la propiedad refleja. Pascal siempre se utiliza para los nombres de propiedad.  
  
 **✓ HACER** nombres de las propiedades mediante un sustantivo, una frase o un adjetivo.  
  
 **X DO NOT** tienen propiedades que coinciden con el nombre de "Get" métodos como en el ejemplo siguiente:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Este patrón normalmente indica que la propiedad debe ser realmente un método.  
  
 **✓ HACER** nombres de las propiedades de colección con una frase plural que describen los elementos de la colección en lugar de usar una frase singular seguida de "Lista" o "Colección".  
  
 **✓ HACER** nombre propiedades booleanas con una frase afirmativa (`CanSeek` en lugar de `CantSeek`). Si lo desea, también se pueden anteponer propiedades booleanas con "Es", "puede" o "Tiene", pero sólo donde se incrementa el valor.  
  
 **Considere la posibilidad de ✓** dar a una propiedad con el mismo nombre que su tipo.  
  
 Por ejemplo, la siguiente propiedad correctamente obtiene y establece un valor de enumeración denominado `Color`, por lo que la propiedad se denomina `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Nombres de eventos  
 Eventos siempre hacen referencia a alguna acción, ya sea uno que sea ocurra, o uno que se ha producido. Por lo tanto, al igual que con los métodos, eventos se denominan con los verbos y tiempo de verbo se utiliza para indicar la hora cuando se produce el evento.  
  
 **✓ HACER** nombrar los eventos con un verbo o una frase.  
  
 Algunos ejemplos son `Clicked`, `Painting`, `DroppedDown`, y así sucesivamente.  
  
 **✓ HACER** asigne nombres de eventos con un concepto de antes y después, con los presentes y tiempos de pasado.  
  
 Por ejemplo, un evento de cierre que se produce antes de cerrar una ventana se denominaría `Closing`, y que se desencadena cuando se cierra la ventana se denominaría `Closed`.  
  
 **X DO NOT** usar "Before" o "After" prefijos o sufijos para indicar previo y eventos posteriores. Use presente y pasado tiempos según se ha descrito.  
  
 **✓ HACER** nombre de controladores de eventos (delegados utilizados como tipos de eventos) con el sufijo "EventHandler", como se muestra en el ejemplo siguiente:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ HACER** utilizar dos parámetros con nombre `sender` y `e` en controladores de eventos.  
  
 El parámetro sender representa el objeto que provocó el evento. El parámetro sender suele ser de tipo `object`, aunque es posible utilizar un tipo más específico.  
  
 **✓ HACER** denominar clases con el sufijo "EventArgs" de los argumentos de evento.  
  
## <a name="names-of-fields"></a>Nombres de campos  
 Se aplican las directrices de nomenclatura de campo a los campos estáticos públicos y protegidos. Campos privados e internos no están cubiertos por instrucciones y campos de instancia público o protegido no se admiten en el [directrices de diseño de miembro](../../../docs/standard/design-guidelines/member.md).  
  
 **✓ HACER** Pascal se utiliza en nombres de campo.  
  
 **✓ HACER** nombres de los campos con un sustantivo, una frase o un adjetivo.  
  
 **X DO NOT** utiliza un prefijo para los nombres de campo.  
  
 Por ejemplo, no utilice "g_" o "s_" para indicar los campos estáticos.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
