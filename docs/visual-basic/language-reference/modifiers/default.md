---
description: 'Más información acerca de: predeterminado (Visual Basic)'
title: Valor predeterminado
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: fe135df4f29ae3c4064c97d4f2789be7f4f3d8f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774608"
---
# <a name="default-visual-basic"></a><span data-ttu-id="f765d-103">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f765d-103">Default (Visual Basic)</span></span>

<span data-ttu-id="f765d-104">Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.</span><span class="sxs-lookup"><span data-stu-id="f765d-104">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f765d-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f765d-105">Remarks</span></span>  

 <span data-ttu-id="f765d-106">Una clase, estructura o interfaz puede designar como máximo una de sus propiedades como la *propiedad predeterminada*, siempre que esa propiedad tome al menos un parámetro.</span><span class="sxs-lookup"><span data-stu-id="f765d-106">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="f765d-107">Si el código hace referencia a una clase o estructura sin especificar un miembro, Visual Basic resuelve esa referencia a la propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f765d-107">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="f765d-108">Las propiedades predeterminadas pueden dar lugar a una pequeña reducción en los caracteres de código fuente, pero pueden hacer que el código sea más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="f765d-108">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="f765d-109">Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de la clase o de la estructura no puede estar seguro de si esa referencia tiene acceso a la clase o estructura, o a una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f765d-109">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="f765d-110">Esto puede provocar errores del compilador o errores de lógica sutiles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f765d-110">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="f765d-111">Puede reducir en cierta medida la posibilidad de que se produzcan errores de propiedad predeterminados Si usa siempre la [instrucción Option Strict](../statements/option-strict-statement.md) para establecer la comprobación del tipo de compilador en `On` .</span><span class="sxs-lookup"><span data-stu-id="f765d-111">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="f765d-112">Si piensa utilizar una clase o estructura predefinida en el código, debe determinar si tiene una propiedad predeterminada y, en ese caso, cuál es su nombre.</span><span class="sxs-lookup"><span data-stu-id="f765d-112">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="f765d-113">Debido a estas desventajas, considere la posibilidad de no definir las propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f765d-113">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="f765d-114">Para facilitar la lectura del código, también debe considerar la posibilidad de hacer referencia siempre a todas las propiedades explícitamente, incluso a las propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f765d-114">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="f765d-115">El `Default` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="f765d-115">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="f765d-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f765d-116">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f765d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f765d-117">See also</span></span>

- [<span data-ttu-id="f765d-118">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f765d-118">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f765d-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f765d-119">Keywords</span></span>](../keywords/index.md)
