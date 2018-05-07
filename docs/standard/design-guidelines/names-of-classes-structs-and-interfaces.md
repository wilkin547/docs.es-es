---
title: Nombres de clases, estructuras e interfaces
ms.date: 03/30/2017
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nombres de clases, estructuras e interfaces
Sigan las instrucciones de nomenclatura que se aplican a la nomenclatura de tipo general.  
  
 **✓ HACER** nombre clases y structs con sustantivos o frases con Pascal.  
  
 Esto permite distinguir los nombres de tipo de métodos, que se denominan con frases verbales.  
  
 **✓ HACER** nombres de las interfaces con frases adjetivo o, en ocasiones con sustantivos o sintagmas nominales.  
  
 Nombres y frases deben se usan con poca frecuencia y podrían indicar que el tipo debe ser una clase abstracta y no una interfaz.  
  
 **X DO NOT** dar a los nombres de clase un prefijo (p. ej., "C").  
  
 **✓ Considere la posibilidad de** finalizar los nombres de las clases derivadas con el nombre de la clase base.  
  
 Esto es muy legible y explica la relación claramente. Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception`, y `SerializableAttribute`, que es un tipo de `Attribute`. Sin embargo, es importante que use un criterio razonable para aplicar esta directriz; Por ejemplo, el `Button` clase es un tipo de `Control` eventos, aunque `Control` no aparece en su nombre.  
  
 **✓ HACER** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.  
  
 Por ejemplo, `IComponent` (sustantivo descriptivo), `ICustomAttributeProvider` (frase), y `IPersistable` (adjetivo) son nombres de interfaz adecuada. Al igual que con otros nombres de tipo, evite las abreviaturas.  
  
 **✓ HACER** Asegúrese de que los nombres difieren solo en la "I" prefijo en el nombre de la interfaz cuando se define un par de interfaz de clase: donde la clase es una implementación estándar de la interfaz.  
  
## <a name="names-of-generic-type-parameters"></a>Nombres de parámetros de tipo genérico  
 Los tipos genéricos se agregaron a .NET Framework 2.0. La característica integra un nuevo tipo de identificador denominado *parámetro de tipo*.  
  
 **✓ HACER** el nombre de parámetros de tipo genérico con nombres descriptivos a menos que sea totalmente explicativa un nombre de letra única y un nombre descriptivo no agregue ningún valor.  
  
 **✓ Considere la posibilidad de** utilizando `T` como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de letra única.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ HACER** prefijo de nombres de parámetros de tipo descriptivos con `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ Considere la posibilidad de** que indica las restricciones de coloca en un parámetro de tipo en el nombre del parámetro.  
  
 Por ejemplo, un parámetro restringido a `ISession` podría denominarse `TSession`.  
  
## <a name="names-of-common-types"></a>Nombres de tipos comunes  
 **✓ HACER** siga las directrices descritas en la tabla siguiente al asignar nombres a los tipos derivados de o implementar determinados tipos de .NET Framework.  
  
|Tipo base|Instrucciones de tipo derivado de implementación|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ HACER** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados.|  
|`System.Delegate`|**✓ HACER** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> **✓ HACER** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.<br /><br /> **X DO NOT** agregar el sufijo "Delegate" a un delegado.|  
|`System.EventArgs`|**✓ HACER** agregar el sufijo "EventArgs".|  
|`System.Enum`|**X DO NOT** derivan de esta clase; use la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C#, utilice el `enum` palabra clave.<br /><br /> **X DO NOT** agregar el sufijo "Enum" o "Flag".|  
|`System.Exception`|**✓ HACER** agregar el sufijo "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ HACER** agregar el sufijo "Diccionario". Tenga en cuenta que `IDictionary` es un tipo específico de la colección, pero esta instrucción tiene prioridad sobre la instrucción de colecciones más general que sigue.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ HACER** agregar el sufijo "Colección".|  
|`System.IO.Stream`|**✓ HACER** agregar el sufijo "Stream".|  
|`CodeAccessPermission IPermission`|**✓ HACER** agregar el sufijo "Permisos".|  
  
## <a name="naming-enumerations"></a>Enumeraciones de nomenclaturas  
 Nombres de tipos de enumeración (también denominados enumeraciones) por lo general deben seguir las reglas de nomenclatura de tipo estándares (Pascal, etcetera). Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.  
  
 **✓ HACER** utilizar un nombre de tipo singular para una enumeración a menos que sus valores son campos de bits.  
  
 **✓ HACER** utilizar un nombre de tipo plural para una enumeración con los campos de bits como valores, también denominados enumeración de marcas.  
  
 **X DO NOT** utilice el sufijo "Enum" en los nombres de tipo de enumeración.  
  
 **X DO NOT** usar "Marca" o sufijos "Indicadores" en la enumeración de nombres de tipo.  
  
 **X DO NOT** utiliza un prefijo en los nombres de valor de enumeración (p. ej., "ad" para las enumeraciones de ADO.), "rtf" para las enumeraciones de texto enriquecido, etcetera.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
