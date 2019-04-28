---
title: System.Convert (Métodos)
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: 9836820f2c084a80fcc0a4856f20597716344dfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877037"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="a22b0-102">System.Convert (Métodos)</span><span class="sxs-lookup"><span data-stu-id="a22b0-102">System.Convert Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a22b0-103">no admite los métodos <xref:System.Convert> siguientes.</span><span class="sxs-lookup"><span data-stu-id="a22b0-103">does not support the following <xref:System.Convert> methods.</span></span>

- <span data-ttu-id="a22b0-104">Versiones con un parámetro <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="a22b0-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>

- <span data-ttu-id="a22b0-105">Métodos que incluyen matrices de caracteres o matrices de bytes:</span><span class="sxs-lookup"><span data-stu-id="a22b0-105">Methods that involve char arrays or byte arrays:</span></span>

  - <xref:System.Convert.FromBase64CharArray%2A>

  - <xref:System.Convert.ToBase64CharArray%2A>

  - <xref:System.Convert.FromBase64String%2A>

  - <xref:System.Convert.ToBase64String%2A>

- <span data-ttu-id="a22b0-106">Los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a22b0-106">The following methods:</span></span>

  - <span data-ttu-id="a22b0-107">`public static <Type2> To<Type2>(<Type1> value);` donde</span><span class="sxs-lookup"><span data-stu-id="a22b0-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>

    <span data-ttu-id="a22b0-108">`Type1` y `Type2` son `sbyte`, `uint`, `ulong` o `ushort`.</span><span class="sxs-lookup"><span data-stu-id="a22b0-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>

  - <span data-ttu-id="a22b0-109">C#:</span><span class="sxs-lookup"><span data-stu-id="a22b0-109">C#:</span></span>

    `int To<int type>(string value, int fromBase),`

    `ToString(... value, int toBase)`

  - <span data-ttu-id="a22b0-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a22b0-110">Visual Basic:</span></span>

    `Function To(Of [Numeric])(value as String, fromBase As Integer)`

    `As [Numeric], ToString( value As …, toBase As Integer)`

  - <xref:System.Convert.IsDBNull%2A>

  - <xref:System.Convert.GetTypeCode%2A>

  - <xref:System.Convert.ChangeType%2A>

## <a name="see-also"></a><span data-ttu-id="a22b0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a22b0-111">See also</span></span>

- [<span data-ttu-id="a22b0-112">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="a22b0-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
