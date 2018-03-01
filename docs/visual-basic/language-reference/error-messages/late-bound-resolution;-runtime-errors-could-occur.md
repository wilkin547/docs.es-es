---
title: "Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="b257f-102">Resolución enlazada tempranamente; pueden producirse errores en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b257f-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="b257f-103">Un objeto se asigna a una variable que se declara de la [tipo de datos de objeto](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b257f-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="b257f-104">Cuando se declara una variable como `Object`, el compilador debe realizar *enlace más tarde*, que produce operaciones adicionales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b257f-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="b257f-105">También expone la aplicación a posibles errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b257f-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="b257f-106">Por ejemplo, si asigna un <xref:System.Windows.Forms.Form> a la `Object` variable y, a continuación, intente obtener acceso a la <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> propiedad, el runtime produce una <xref:System.MemberAccessException> porque el <xref:System.Windows.Forms.Form> clase no expone un `NameTable` propiedad.</span><span class="sxs-lookup"><span data-stu-id="b257f-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="b257f-107">Si se declara la variable para que sea de un tipo específico, el compilador puede realizar *el enlace anticipado* en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b257f-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="b257f-108">Esto da como resultado un mejor rendimiento, acceso controlado a los miembros del tipo específico y mejorar la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="b257f-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="b257f-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="b257f-109">By default, this message is a warning.</span></span> <span data-ttu-id="b257f-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b257f-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b257f-111">**Id. de error:** BC42017</span><span class="sxs-lookup"><span data-stu-id="b257f-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b257f-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b257f-112">To correct this error</span></span>  
  
-   <span data-ttu-id="b257f-113">Si es posible, declare la variable de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="b257f-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b257f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b257f-114">See Also</span></span>  
 [<span data-ttu-id="b257f-115">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b257f-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="b257f-116">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b257f-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
