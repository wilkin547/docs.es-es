---
title: "C&#243;mo: Convertir una matriz de bytes en un valor int (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices de bytes [C#], convertir a int"
  - "conversiones [C#], matriz de bytes a int"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# C&#243;mo: Convertir una matriz de bytes en un valor int (Gu&#237;a de programaci&#243;n de C#)
Este ejemplo muestra cómo utilizar la clase <xref:System.BitConverter> para convertir una matriz de bytes en un valor [int](../../../csharp/language-reference/keywords/int.md) y de nuevo en una matriz de bytes.  Por ejemplo, es posible que tenga que realizar una conversión de bytes a un tipo de datos integrado después de leer los bytes fuera de la red.  Además del método [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> del ejemplo, en la tabla siguiente se muestran los métodos de la clase <xref:System.BitConverter> que sirven para convertir bytes \(de una matriz de bytes\) en otros tipos integrados.  
  
|Tipo devuelto|Método|  
|-------------------|------------|  
|`bool`|[ToBoolean\(Byte\<xref:System.BitConverter.ToBoolean%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`char`|[ToChar\(Byte\<xref:System.BitConverter.ToChar%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`double`|[ToDouble\(Byte\<xref:System.BitConverter.ToDouble%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`short`|[ToInt16\(Byte\<xref:System.BitConverter.ToInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`int`|[ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`long`|[ToInt64\(Byte\<xref:System.BitConverter.ToInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`float`|[ToSingle\(Byte\<xref:System.BitConverter.ToSingle%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ushort`|[ToUInt16\(Byte\<xref:System.BitConverter.ToUInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`uint`|[ToUInt32\(Byte\<xref:System.BitConverter.ToUInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ulong`|[ToUInt64\(Byte\<xref:System.BitConverter.ToUInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
  
## Ejemplo  
 Este ejemplo inicializa una matriz de bytes, invierte la matriz si la arquitectura de equipo es little\-endian \(es decir, en primer lugar se almacena el byte menos significativo\), y, a continuación, llama al método [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> para convertir cuatro bytes de la matriz en `int`.  El segundo argumento de [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> especifica el índice de inicio de la matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes \(big\-endian o little\-endian\) de la arquitectura de equipo.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_1.cs)]  
  
## Ejemplo  
 En este ejemplo, se llama al método <xref:System.BitConverter.GetBytes%28System.Int32%29> de la clase <xref:System.BitConverter> para convertir `int` en una matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes \(big\-endian o little\-endian\) de la arquitectura de equipo.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_2.cs)]  
  
## Vea también  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Tipos](../../../csharp/programming-guide/types/index.md)