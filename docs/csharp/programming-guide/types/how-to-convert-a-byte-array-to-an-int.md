---
title: "Cómo: Convertir una matriz de bytes en un valor int (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2d26bb4821e09c6633d1c5a4dd40e132e57acf94
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Cómo: Convertir una matriz de bytes en un valor int (Guía de programación de C#)
En este ejemplo se muestra cómo usar la clase <xref:System.BitConverter> para convertir una matriz de bytes en un valor [int](../../../csharp/language-reference/keywords/int.md) y de nuevo en una matriz de bytes. Por ejemplo, es posible que tenga que realizar una conversión de bytes a un tipo de datos integrado después de leer los bytes fuera de la red. Además del método [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) del ejemplo, en la tabla siguiente se muestran los métodos de la clase <xref:System.BitConverter> que sirven para convertir bytes (de una matriz de bytes) en otros tipos integrados.  
  
|Tipo devuelto|Método|  
|-------------------|------------|  
|`bool`|[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|  
|`char`|[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|  
|`double`|[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|  
|`short`|[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|  
|`int`|[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|  
|`long`|[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|  
|`float`|[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|  
|`ushort`|[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|  
|`uint`|[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|  
|`ulong`|[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se inicializa una matriz de bytes, invierte la matriz si la arquitectura de equipo es little-endian (es decir, en primer lugar se almacena el byte menos significativo) y, después, llama al método [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) para convertir cuatro bytes de la matriz en `int`. El segundo argumento de [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) especifica el índice de inicio de la matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes de la arquitectura del equipo.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se llama al método <xref:System.BitConverter.GetBytes%28System.Int32%29> de la clase <xref:System.BitConverter> para convertir `int` en una matriz de bytes.  
  
> [!NOTE]
>  El resultado puede cambiar en función del orden de bytes de la arquitectura del equipo.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Tipos](../../../csharp/programming-guide/types/index.md)

