---
title: Nombres de miembros de tipos
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: a9cd531100057fbad4884a20e6e7db6ef94e7956
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709223"
---
# <a name="names-of-type-members"></a>Nombres de miembros de tipos
Los tipos están conformados por miembros: métodos, propiedades, eventos, constructores y campos. En las siguientes secciones se detallan las instrucciones para asignar un nombre a los miembros de tipos.  
  
## <a name="names-of-methods"></a>Nombres de métodos  
 Dado que los métodos son medios para emprender una acción, las instrucciones de diseño requieren que los nombres sean verbos o enunciados verbales. Esto también permite distinguir los nombres de métodos de los de propiedades y tipos, que emplean sintagmas nominales o adjetivales.  
  
 **✓ DO** Los nombres de métodos deben ser verbos o enunciados verbales.  
  
```csharp  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Nombres de propiedades  
 A diferencia de otros miembros, las propiedades deben tener nombres en forma de sintagmas nominales o adjetivales. El motivo es que las propiedades hacen referencia a datos, y el nombre de estas deben reflejarlo adecuadamente. Los nombres de propiedades siempre se escriben con el formato PascalCase, es decir, las palabras se escriben unidas y se diferencian las unas de las otras por el uso de la mayúscula inicial. Este formato también es conocido como CamelCase.  
  
 **✓ DO** Los nombres de propiedades deben ser sustantivos, o sintagmas nominales o adjetivales.  
  
 **X DO NOT** Los nombres de propiedades no deben coincidir con los de otros métodos "Get", como se muestra en el ejemplo siguiente:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Este patrón suele indicar que la propiedad en realidad debería ser un método.  
  
 **✓** Las propiedades de la colección de nombres con una frase plural que describe los elementos de la colección en lugar de usar una frase singular seguida de "list" o "Collection".  
  
 **✓ DO** Los nombres de propiedades booleanas deben ser un enunciado positivo, es decir, `CanSeek` en lugar de `CantSeek`. Opcionalmente, también puede prefijar las propiedades booleanas con "es", "puede" o "tiene", pero solo cuando agrega valor.  
  
 **✓ CONSIDER** El nombre de una propiedad puede ser el mismo que el del tipo.  
  
 Por ejemplo, la propiedad siguiente permite obtener y establecer un valor de enumeración denominado `Color`, de modo que el nombre de la propiedad es `Color`:  
  
```csharp  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Nombres de eventos  
 Los eventos siempre hacen referencia a algún tipo de acción, ya sea una acción en curso o una ya finalizada. Así pues, como en el caso de los métodos, para los nombres de los eventos se utilizan verbos, y el tiempo verbal permite indicar el momento de la acción.  
  
 **✓ DO** Los nombres de eventos deben ser verbos o enunciados verbales.  
  
 Por ejemplo, `Clicked`, `Painting`, `DroppedDown`,etc.  
  
 **✓ DO** Los nombres de eventos deben incluir el concepto del antes y el después mediante tiempos verbales que indiquen presente y futuro.  
  
 Por ejemplo, un evento de cierre que tuviera lugar antes de cerrar una ventana se llamaría `Closing`, mientras que uno que lo hiciera después se llamaría `Closed`.  
  
 **X DO NOT** Los nombres de eventos no deben incluir "antes" ni "después", ya sea en forma de prefijo o de sufijo, para indicar el momento del evento. Utilice tiempos verbales que indiquen presente y futuro, como se ha explicado.  
  
 **✓ DO** Los controladores de eventos, es decir, los delegados que se usan como tipos de eventos, pueden incluir el sufijo "ControladorDeEventos", como se muestra en el ejemplo siguiente:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ DO** En el caso de los controladores de eventos, use dos parámetros denominados `sender` y `e`.  
  
 El parámetro de envío corresponde al objeto que genera el evento. Este suele ser del tipo `object`, incluso aunque sea posible utilizar un tipo que sea más específico.  
  
 **✓ DO** Las clases de argumentos de eventos pueden incluir el sufijo "ArgDeEvento".  
  
## <a name="names-of-fields"></a>Nombres de campos  
 Las instrucciones relativas a la nomenclatura de los campos son aplicables a los campos estáticos públicos y protegidos. En las instrucciones no se abordan los campos internos y privados. Asimismo, las [instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md) no permiten los campos de instancias públicas o protegidas.  
  
 **✓ DO** Los nombres de campos se escriben con el formato PascalCase, es decir, las palabras se escriben unidas y se diferencian las unas de las otras por el uso de la mayúscula inicial. Este formato también es conocido como CamelCase.  
  
 **✓ DO** Los nombres de campos deben ser sustantivos, o sintagmas nominales o adjetivales.  
  
 **X DO NOT** Los nombres de campos no deben incluir prefijos.  
  
 Por ejemplo, no utilice "g_" ni "s_" para indicar campos estáticos.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
