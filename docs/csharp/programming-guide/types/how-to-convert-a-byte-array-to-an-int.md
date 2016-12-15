---
title: "C&#243;mo: Convertir una matriz de bytes en un valor int (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices de bytes [C#], convertir a int"
  - "conversiones [C#], matriz de bytes a int"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Convertir una matriz de bytes en un valor int (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo muestra cómo utilizar la clase <xref:System.BitConverter> para convertir una matriz de bytes en un valor [int](../../../csharp/language-reference/keywords/int.md) y de nuevo en una matriz de bytes.  Por ejemplo, es posible que tenga que realizar una conversión de bytes a un tipo de datos integrado después de leer los bytes fuera de la red.  Además del método [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) del ejemplo, en la tabla siguiente se muestran los métodos de la clase <xref:System.BitConverter> que sirven para convertir bytes \(de una matriz de bytes\) en otros tipos integrados.  
  
|Tipo devuelto|Método|  
|-------------------|------------|  
|`bool`|[ToBoolean\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToBoolean(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`char`|[ToChar\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToChar(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`double`|[ToDouble\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToDouble(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`short`|[ToInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`int`|[ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`long`|[ToInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`float`|[ToSingle\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToSingle(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ushort`|[ToUInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`uint`|[ToUInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ulong`|[ToUInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
  
## Ejemplo  
 Este ejemplo inicializa una matriz de bytes, invierte la matriz si la arquitectura de equipo es little\-endian \(es decir, en primer lugar se almacena el byte menos significativo\), y, a continuación, llama al método [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) para convertir cuatro bytes de la matriz en `int`.  El segundo argumento de [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) especifica el índice de inicio de la matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes \(big\-endian o little\-endian\) de la arquitectura de equipo.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## Ejemplo  
 En este ejemplo, se llama al método <xref:System.BitConverter.GetBytes%28System.Int32%29> de la clase <xref:System.BitConverter> para convertir `int` en una matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes \(big\-endian o little\-endian\) de la arquitectura de equipo.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## Vea también  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Tipos](../../../csharp/programming-guide/types/index.md)