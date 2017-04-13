---
title: "Tipos de colecciones ordenadas | Microsoft Docs"
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
  - "colecciones [.NET Framework], SortedList (tipo de colección)"
  - "agrupar datos en colecciones, SortedList (tipo de colección)"
  - "SortedDictionary (tipo de colección)"
  - "SortedList (clase), agrupar datos en colecciones"
  - "SortedList (tipo de colección)"
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Tipos de colecciones ordenadas
La clase <xref:System.Collections.SortedList?displayProperty=fullName>, la clase genérica <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> y la clase genérica <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> se parecen a la clase <xref:System.Collections.Hashtable> y a la clase genérica <xref:System.Collections.Generic.Dictionary%602> en que implementan la interfaz <xref:System.Collections.IDictionary>, pero mantienen sus elementos ordenados por clave y no disponen de las características de inserción y recuperación O\(1\) de las tablas hash.  Estas tres clases tienen varias características en común:  
  
-   Las tres implementan la interfaz <xref:System.Collections.IDictionary?displayProperty=fullName>.  Las dos clases genéricas también implementan la interfaz genérica <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>.  
  
-   Cada elemento es un par de clave y valor para propósitos de enumeración.  
  
    > [!NOTE]
    >  La clase <xref:System.Collections.SortedList> no genérica devuelve objetos <xref:System.Collections.DictionaryEntry> cuando se enumera, aunque los dos tipos genéricos devuelven objetos <xref:System.Collections.Generic.KeyValuePair%602>.  
  
-   Los elementos se ordenan conforme a una implementación de <xref:System.Collections.IComparer?displayProperty=fullName> \(para la clase <xref:System.Collections.SortedList> no genérica\) o una implementación de <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> \(para las dos clases genéricas\).  
  
-   Cada clase proporciona propiedades que devuelven colecciones que sólo contienen las claves o los valores.  
  
 En la siguiente tabla se muestran algunas de las diferencias que existen entre las dos clases de lista ordenada y la clase <xref:System.Collections.Generic.SortedDictionary%602>.  
  
|Clase <xref:System.Collections.SortedList> no genérica y clase genérica <xref:System.Collections.Generic.SortedList%602>|Clase genérica <xref:System.Collections.Generic.SortedDictionary%602>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Las propiedades que devuelven claves y valores se indizan, lo que permite una recuperación indizada eficaz.|Sin recuperación indizada.|  
|La recuperación es O\(log `n`\).|La recuperación es O\(log `n`\).|  
|Normalmente, la inserción y la eliminación son O\(`n`\); sin embargo, la inserción es O\(1\) para los datos que ya están ordenados, de modo que cada elemento se agrega al final de la lista. \(Esto significa que no se requiere un cambio de tamaño.\)|La inserción y la eliminación son O\(log `n`\).|  
|Utiliza menos memoria que <xref:System.Collections.Generic.SortedDictionary%602>.|Utiliza más memoria que la clase <xref:System.Collections.SortedList> no genérica y que la clase genérica <xref:System.Collections.Generic.SortedList%602>.|  
  
 Para listas ordenadas o diccionarios que deben ser accesibles simultáneamente desde varios subprocesos, puede agregar lógica de ordenación a una clase que deriva de <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.  
  
> [!NOTE]
>  En el caso de los valores que contienen sus propias claves \(por ejemplo, registros de empleados que contienen un número de identificación de empleado\), puede crear una colección con clave que tenga algunas de las características de una lista y algunas de las características de un diccionario; para ello, tiene que realizar derivaciones de la clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
 A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la clase <xref:System.Collections.Generic.SortedSet%601> proporciona un árbol que mantiene los datos ordenados después de que se hayan realizado operaciones de inserción, eliminación y búsqueda.  Esta clase y la clase <xref:System.Collections.Generic.HashSet%601> implementan la interfaz <xref:System.Collections.Generic.ISet%601>.  
  
## Vea también  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [Tipos de colección utilizados normalmente](../../../docs/standard/collections/commonly-used-collection-types.md)