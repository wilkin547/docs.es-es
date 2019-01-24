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
# <a name="systemconvert-methods"></a><span data-ttu-id="617dd-102">System.Convert (Métodos)</span><span class="sxs-lookup"><span data-stu-id="617dd-102">System.Convert Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="617dd-103">no admite los métodos <xref:System.Convert> siguientes.</span><span class="sxs-lookup"><span data-stu-id="617dd-103">does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="617dd-104">Versiones con un parámetro <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="617dd-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="617dd-105">Métodos que incluyen matrices de caracteres o matrices de bytes:</span><span class="sxs-lookup"><span data-stu-id="617dd-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="617dd-106">Los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="617dd-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="617dd-107">`public static <Type2> To<Type2>(<Type1> value);` donde</span><span class="sxs-lookup"><span data-stu-id="617dd-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="617dd-108">`Type1` y `Type2` son `sbyte`, `uint`, `ulong` o `ushort`.</span><span class="sxs-lookup"><span data-stu-id="617dd-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="617dd-109">C#:</span><span class="sxs-lookup"><span data-stu-id="617dd-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="617dd-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="617dd-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="617dd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="617dd-111">See also</span></span>
- [<span data-ttu-id="617dd-112">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="617dd-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
