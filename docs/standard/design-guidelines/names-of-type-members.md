---
title: "Nombres de miembros de tipo | Microsoft Docs"
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
  - "eventos [.NET Framework], nombres"
  - "métodos [.NET Framework], nombres"
  - "miembros de tipo"
  - "propiedades [.NET Framework], nombres"
  - "campos, nombres"
  - "nombres de campo"
  - "nombres [.NET Framework], los miembros de tipo"
  - "tipo de miembros [.NET Framework]"
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Nombres de miembros de tipo
Se realizan los tipos de miembros: métodos, propiedades, eventos, constructores y campos. Las secciones siguientes describen las directrices para asignar nombres a los miembros de tipo.  
  
## Nombres de métodos  
 Dado que son los medios para realizar una acción, las instrucciones de diseño requieren que los nombres de método se verbos o sintagmas verbales. Siga esta directriz también sirve para distinguir los nombres de método de nombres de propiedad y tipo, que son frases sustantivo o adjetivo.  
  
 **✓ hacer** proporcione nombres de métodos que sean verbos o sintagmas verbales.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
  
```  
  
## Nombres de propiedades  
 A diferencia de otros miembros, propiedades deben tener nombres adjetivo o frase. Eso es porque una propiedad hace referencia a los datos y el nombre de la propiedad refleja. Pascal siempre se utiliza para los nombres de propiedad.  
  
 **✓ hacer** nombres de las propiedades mediante un sustantivo, frase o adjetivo.  
  
 **X no** tienen propiedades que coinciden con el nombre de los métodos "Get", como en el ejemplo siguiente:  
  
 `public string TextWriter { get {...} set {...} }`   
 `public string GetTextWriter(int value) { ... }`  
  
 Este patrón normalmente indica que la propiedad debe ser realmente un método.  
  
 **✓ hacer** nombres de las propiedades de colección con una frase plural que describen los elementos de la colección en lugar de usar una frase singular seguida de "Lista" o "Colección".  
  
 **✓ hacer** nombre propiedades booleanas con una frase afirmativa \(`CanSeek` en lugar de `CantSeek`\). Opcionalmente, también se pueden anteponer propiedades booleanas con "Es", "puede" o "Tiene", pero sólo cuando agrega el valor.  
  
 **✓, considere la posibilidad de** que proporciona una propiedad el mismo nombre que su tipo.  
  
 Por ejemplo, la siguiente propiedad correctamente obtiene y establece un valor de enumeración denominado `Color`, por lo que la propiedad se denomina `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## Nombres de eventos  
 Eventos siempre hacen referencia a una acción, ya sea que está sucediendo o que se ha producido. Por lo tanto, al igual que con los métodos, eventos se denominan con verbos y tiempo verbal verbo se usa para indicar la hora cuando se produce el evento.  
  
 **✓ hacer** nombrar los eventos con un verbo o una frase.  
  
 Algunos ejemplos son `Clicked`, `Painting`, `DroppedDown`, y así sucesivamente.  
  
 **✓ hacer** dar nombres de eventos con un concepto de antes y después, mediante el presente y tiempos del pasado.  
  
 Por ejemplo, un evento de cierre que se desencadena antes de cerrar una ventana se llamaría `Closing`, y que se produce después de cerrar la ventana se llamará `Closed`.  
  
 **X no** usar "Before" o "After" prefijos o sufijos para indicar previo y eventos posteriores. Uso presente y pasado tiempos descrita anteriormente.  
  
 **✓ hacer** nombre de controladores de eventos \(los delegados utilizados como tipos de eventos\) con el sufijo "EventHandler", como se muestra en el ejemplo siguiente:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ hacer** utiliza dos parámetros denominados `sender` y `e` en controladores de eventos.  
  
 El parámetro sender representa el objeto que provocó el evento. El parámetro sender suele ser de tipo `object`, aunque es posible utilizar un tipo más específico.  
  
 **✓ hacer** nombres de las clases de argumento con el sufijo "EventArgs" de evento.  
  
## Nombres de campos  
 Se aplican las directrices de nomenclatura de campo a los campos estáticos públicos y protegidos. Los campos internos y privados no están cubiertos por las directrices y no se admiten los campos de instancia públicos o protegidos por el [instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md).  
  
 **✓ hacer** Pascal se utiliza en nombres de campo.  
  
 **✓ hacer** nombres de los campos con un sustantivo, frase o adjetivo.  
  
 **X no** utiliza un prefijo para los nombres de campo.  
  
 Por ejemplo, no utilice "g\_" o "s\_" para indicar los campos estáticos.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)