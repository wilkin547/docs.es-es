---
title: "Realizar cambios de may&#250;sculas y min&#250;sculas que no tienen en cuenta las referencias culturales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "String.ToLower (método)"
  - "referencia cultural, distinción entre mayúsculas y minúsculas"
  - "Char.ToLower (método)"
  - "mayúsculas y minúsculas, cambios en cadenas que no tienen en cuenta la referencia cultural"
  - "Char.ToUpper (método)"
  - "operaciones en cadenas que no tienen en cuenta la referencia cultural, cambios de mayúsculas y minúsculas"
  - "String.ToUpper (método)"
  - "parámetro de referencia cultural"
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Realizar cambios de may&#250;sculas y min&#250;sculas que no tienen en cuenta las referencias culturales
Los métodos <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> y <xref:System.Char.ToLower%2A?displayProperty=fullName> disponen de sobrecargas que no aceptan ningún parámetro.  De forma predeterminada, estas sobrecargas sin parámetros realizan cambios de mayúsculas y minúsculas en función del valor de <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.  Esto produce resultados que tienen en cuenta las mayúsculas y minúsculas y que pueden cambiar en función de la referencia cultural.  Para aclarar si desea cambios de mayúsculas y minúsculas que tengan en cuenta las referencias culturales o que no las tengan en cuenta, debe usar las sobrecargas de esos métodos que necesitan la especificación explícita de un parámetro `culture`.  En el caso de cambios en el uso de mayúsculas y minúsculas dependientes de la referencia cultural, especifique `CultureInfo.CurrentCulture` para el parámetro `culture`.  Si se trata de cambios en el uso de mayúsculas y minúsculas independientes de la referencia cultural, especifique `CultureInfo.InvariantCulture` para el parámetro `culture`.  
  
 A menudo, las cadenas se convierten a un uso estándar de mayúsculas y minúsculas, para permitir una búsqueda más fácil posteriormente.  Cuando se usan las cadenas de este modo, se debe especificar `CultureInfo.InvariantCulture` para el parámetro `culture`, ya que el valor de <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName> podría cambiar desde el momento en que se hacen los cambios de mayúsculas y minúsculas hasta el momento en que se realiza la búsqueda.  
  
 Si una decisión de seguridad se basa en una operación de cambio de mayúsculas y minúsculas, la operación debe ser independiente de la referencia cultural para asegurarse de que el resultado no se vea afectado por el valor de `CultureInfo.CurrentCulture`.  Consulte la sección "Comparaciones de cadenas que usan la referencia cultural actual" del artículo [Procedimientos recomendados para el uso de cadenas](../../../docs/standard/base-types/best-practices-strings.md) para obtener un ejemplo que muestra cómo las operaciones de comparación de cadenas que tienen en cuenta la referencia cultural pueden generar resultados incoherentes.  
  
## Utilizar los métodos String.ToUpper y String.ToLower  
 Para lograr claridad en el código, se recomienda usar siempre sobrecargas de los métodos `String.ToUpper` y `String.ToLower` que permiten especificar explícitamente un parámetro `culture`.  Por ejemplo, en el siguiente código se realiza la búsqueda de un identificador.  La operación `key.ToLower` tiene en cuenta las referencias culturales de manera predeterminada, pero este comportamiento no está claro leyendo el código.  
  
### Ejemplo  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 Si desea que la operación `key.ToLower` sea independiente de la referencia cultural, debe cambiar el ejemplo anterior de la manera siguiente para usar explícitamente `CultureInfo.InvariantCulture` cuando se cambien las mayúsculas y minúsculas.  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## Utilizar los métodos Char.ToUpper y Char.ToLower  
 Aunque los métodos `Char.ToUpper` y `Char.ToLower`  tienen las mismas características que los métodos `String.ToLower` y `String.ToUpper`, las únicas referencias culturales afectadas son la de turco \(Turquía\) y azerbaiyano \(latino, Azerbaiyán\).  Estas son las dos únicas referencias culturales con diferencias de mayúsculas y minúsculas en un solo carácter.  Para obtener información más detallada sobre esta asignación única de mayúsculas y minúsculas, vea la sección "Uso de mayúsculas y minúsculas" en el tema de la clase <xref:System.String>.  Para lograr claridad en el código y asegurar resultados coherentes, se recomienda usar siempre las sobrecargas de estos métodos que permiten especificar explícitamente un parámetro `culture`.  
  
## Vea también  
 <xref:System.String.ToUpper%2A?displayProperty=fullName>   
 <xref:System.String.ToLower%2A?displayProperty=fullName>   
 <xref:System.Char.ToUpper%2A?displayProperty=fullName>   
 <xref:System.Char.ToLower%2A?displayProperty=fullName>   
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)