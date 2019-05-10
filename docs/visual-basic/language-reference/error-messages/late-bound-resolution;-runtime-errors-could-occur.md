---
title: Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 6b78dfed1d615ba865f136365eac1c9c131ed5a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661946"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="a6a97-102">Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a6a97-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="a6a97-103">Un objeto se asigna a una variable que se declara de la [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a6a97-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="a6a97-104">Cuando se declara una variable como `Object`, el compilador debe realizar *enlace más tarde*, que produce operaciones adicionales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6a97-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="a6a97-105">También expone la aplicación a posibles errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6a97-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="a6a97-106">Por ejemplo, si asigna un <xref:System.Windows.Forms.Form> a la `Object` variable y, a continuación, intente obtener acceso a la <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> propiedad, el tiempo de ejecución produce una <xref:System.MemberAccessException> porque el <xref:System.Windows.Forms.Form> clase no expone un `NameTable` propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6a97-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="a6a97-107">Si se declara la variable es de un tipo específico, el compilador puede realizar *enlace anticipado* en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a6a97-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="a6a97-108">Esto da como resultado un mejor rendimiento, acceso controlado a los miembros del tipo específico y mejorar la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="a6a97-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="a6a97-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="a6a97-109">By default, this message is a warning.</span></span> <span data-ttu-id="a6a97-110">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a6a97-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a6a97-111">**Identificador de error:** BC42017</span><span class="sxs-lookup"><span data-stu-id="a6a97-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6a97-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a6a97-112">To correct this error</span></span>  
  
- <span data-ttu-id="a6a97-113">Si es posible, declare la variable sea de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="a6a97-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a97-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6a97-114">See also</span></span>

- [<span data-ttu-id="a6a97-115">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a6a97-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="a6a97-116">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="a6a97-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
