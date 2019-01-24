---
title: System.Convert (Métodos)
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: c3b8c7105578c57547b79bc95b633bcc6449a0ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591726"
---
# <a name="systemconvert-methods"></a>System.Convert (Métodos)
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite los métodos <xref:System.Convert> siguientes.  
  
-   Versiones con un parámetro <xref:System.IFormatProvider>.  
  
-   Métodos que incluyen matrices de caracteres o matrices de bytes:  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   Los métodos siguientes:  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` donde  
  
         `Type1` y `Type2` son `sbyte`, `uint`, `ulong` o `ushort`.  
  
    -   C#:  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   Visual Basic:  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a>Vea también
- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
