---
title: "Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="02dda-102">Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02dda-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="02dda-103">Este ejemplo crea una cadena larga de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="02dda-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="02dda-104">El <xref:System.Text.StringBuilder> clase es más eficaz que la `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="02dda-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02dda-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02dda-105">Example</span></span>  
 <span data-ttu-id="02dda-106">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexan 1.000 cadenas a esa instancia y, a continuación, devuelve la representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="02dda-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="02dda-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="02dda-107">See Also</span></span>  
 [<span data-ttu-id="02dda-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="02dda-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="02dda-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="02dda-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="02dda-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="02dda-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="02dda-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="02dda-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="02dda-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="02dda-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 [<span data-ttu-id="02dda-113">Ejemplo de cadenas</span><span class="sxs-lookup"><span data-stu-id="02dda-113">Strings Sample</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
