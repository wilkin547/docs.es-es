---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a><span data-ttu-id="f19d5-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f19d5-102">Default (Visual Basic)</span></span>
<span data-ttu-id="f19d5-103">Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.</span><span class="sxs-lookup"><span data-stu-id="f19d5-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f19d5-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f19d5-104">Remarks</span></span>  
 <span data-ttu-id="f19d5-105">Una clase, estructura o interfaz puede designar al menos uno de sus propiedades como el *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro.</span><span class="sxs-lookup"><span data-stu-id="f19d5-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="f19d5-106">Si el código hace referencia a una clase o estructura sin especificar a un miembro, Visual Basic resuelve que hacen referencia a la propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f19d5-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="f19d5-107">Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que el código más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="f19d5-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="f19d5-108">Si el código de llamada no está familiarizado con la clase o estructura, cuando hace referencia al nombre de clase o estructura no podrá saber si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f19d5-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="f19d5-109">Esto puede conducir a errores del compilador o errores sutiles lógicos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f19d5-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="f19d5-110">Algo puede reducir la posibilidad de errores de propiedades de forma predeterminada al usar siempre el [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador comprobación `On`.</span><span class="sxs-lookup"><span data-stu-id="f19d5-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="f19d5-111">Si planea usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.</span><span class="sxs-lookup"><span data-stu-id="f19d5-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="f19d5-112">Debido a estas desventajas, considere la posibilidad de no definir propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f19d5-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="f19d5-113">Para la legibilidad del código, debe tener en cuenta siempre que hace referencia a todas las propiedades de forma explícita, incluso predeterminados propiedades.</span><span class="sxs-lookup"><span data-stu-id="f19d5-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="f19d5-114">El `Default` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="f19d5-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="f19d5-115">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f19d5-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f19d5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f19d5-116">See Also</span></span>  
 [<span data-ttu-id="f19d5-117">Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f19d5-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="f19d5-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f19d5-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
