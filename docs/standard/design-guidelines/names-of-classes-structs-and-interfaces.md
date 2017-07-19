---
title: "Nombres de clases, Structs e Interfaces | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
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
  - "nombres de tipo, instrucciones"
  - "clases [.NET Framework], nombres"
  - "enumeraciones [.NET Framework], nombres"
  - "nombres [.NET Framework], interfaces"
  - "nombres de tipo comunes"
  - "nombres [.NET Framework], nombres de tipo"
  - "nombres [.NET Framework], clases"
  - "interfaces [.NET Framework], nombres"
  - "parámetros de tipo genérico"
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Nombres de clases, Structs e Interfaces
Sigan las instrucciones de nomenclatura que se aplican a la nomenclatura de tipo general.  
  
 **✓ hacer** nombre clases y structs con sustantivos o sintagmas nominales, con Pascal.  
  
 Esto distingue a nombres de tipo de métodos, que se denominan con frases verbales.  
  
 **✓ hacer** nombres de las interfaces con frases adjetivo u ocasional con sustantivos o sintagmas nominales.  
  
 Nombres y frases deben usarse a menudo y podrían indicar que el tipo debe ser una clase abstracta y no una interfaz.  
  
 **X no** dar a los nombres de clase un prefijo \(por ejemplo, "C"\).  
  
 **✓ considere** finalizar los nombres de las clases derivadas con el nombre de la clase base.  
  
 Esto es muy legible y explica claramente de la relación. Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception`, y `SerializableAttribute`, que es un tipo de `Attribute`. Sin embargo, es importante utilizar la lógica en la aplicación de esta instrucción; Por ejemplo, el `Button` clase es un tipo de `Control` evento, aunque `Control` no aparece en su nombre.  
  
 **✓ hacer** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.  
  
 Por ejemplo, `IComponent` \(sustantivo descriptivo\), `ICustomAttributeProvider` \(frase\), y `IPersistable` \(adjetivo\) son nombres de interfaz adecuada. Al igual que con otros nombres de tipo, evite las abreviaturas.  
  
 **✓ hacer** Asegúrese de que los nombres difieren solo en la "I" prefijo en el nombre de interfaz al definir un par de interfaz de clase, donde la clase es una implementación estándar de la interfaz.  
  
## Nombres de parámetros de tipo genérico  
 Se agregaron los genéricos en .NET Framework 2.0. La característica introdujo un nuevo tipo de identificador denominada *parámetro de tipo*.  
  
 **✓ hacer** nombre de parámetros de tipo genérico con nombres descriptivos, a menos que sea totalmente explicativa un nombre de letra única y un nombre descriptivo no agregue ningún valor.  
  
 **✓ considere** utilizando `T` como nombre del parámetro de tipo para los tipos con un parámetro de tipo de letra única.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ hacer** prefijo de nombres de parámetros de tipo descriptivos con `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓, considere la posibilidad de** que indica las restricciones se coloca en un parámetro de tipo en el nombre del parámetro.  
  
 Por ejemplo, un parámetro restringido a `ISession` podría denominarse `TSession`.  
  
## Nombres de tipos comunes  
 **✓ hacer** siga las instrucciones descritas en la tabla siguiente al asignar nombres a tipos derivados de o implementar determinados tipos de .NET Framework.  
  
|Tipo base|Directriz de tipo derivado y la implementación|  
|---------------|----------------------------------------------------|  
|`System.Attribute`|**✓ hacer** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados. Agregue el sufijo "Attribute" a los nombres de clases de atributos personalizados.|  
|`System.Delegate`|**✓ hacer** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> **✓ hacer** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.<br /><br /> **X no** agregar el sufijo "Delegate" a un delegado.|  
|`System.EventArgs`|**✓ hacer** agregar el sufijo "EventArgs".|  
|`System.Enum`|**X no** derivan de esta clase; utilice la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C\#, utilice la palabra clave enum.<br /><br /> **X no** agregar el sufijo "Enum" o "Flag".|  
|`System.Exception`|**✓ hacer** agregar el sufijo "Excepción".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ hacer** agregar el sufijo "Diccionario". Tenga en cuenta que `IDictionary` es un tipo específico de la colección, pero esta instrucción tiene prioridad sobre la instrucción de colecciones más general que sigue.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ hacer** agregar el sufijo "Colección".|  
|`System.IO.Stream`|**✓ hacer** agregar el sufijo "Stream".|  
|`CodeAccessPermission IPermission`|**✓ hacer** agregar el sufijo "Permiso".|  
  
## Nombres de enumeraciones  
 Nombres de tipos de enumeración \(también denominados enumeraciones\) en general deben seguir las reglas de nomenclatura de tipo estándar \(Pascal, etc.\). Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.  
  
 **✓ hacer** utilizar un nombre de tipo singular para una enumeración a menos que sus valores son campos de bits.  
  
 **✓ hacer** utilizar un nombre de tipo plural para una enumeración con campos de bits como valores, también denominados enumeración de marcas.  
  
 **X no** utilice el sufijo "Enum" en los nombres de tipo enum.  
  
 **X no** use "Marcar" o sufijos "Indicadores" en la enumeración de nombres de tipo.  
  
 **X no** utilice un prefijo en los nombres de valores de enumeración \(por ejemplo, "ad" para las enumeraciones ADO.\), "rtf" para las enumeraciones de texto enriquecido, etc..  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)