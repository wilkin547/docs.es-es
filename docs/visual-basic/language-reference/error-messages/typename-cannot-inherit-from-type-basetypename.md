---
title: "&#39; &lt;typename&gt;&#39; no puede heredar de &lt;tipo&gt; &#39;&lt; nombreDeTipoBase&gt;&#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords: BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a><span data-ttu-id="b57be-102">&#39; &lt;typename&gt;&#39; no puede heredar de &lt;tipo&gt; &#39;&lt; nombreDeTipoBase&gt;&#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado</span><span class="sxs-lookup"><span data-stu-id="b57be-102">&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly</span></span>
<span data-ttu-id="b57be-103">Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.</span><span class="sxs-lookup"><span data-stu-id="b57be-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="b57be-104">Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de una `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="b57be-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="b57be-105">Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.</span><span class="sxs-lookup"><span data-stu-id="b57be-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="b57be-106">**Id. de error:** BC30910</span><span class="sxs-lookup"><span data-stu-id="b57be-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b57be-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b57be-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b57be-108">Cambiar el nivel de acceso de la clase o interfaz derivada para que sea al menos tan restrictiva como la de la clase base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="b57be-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="b57be-109">O bien</span><span class="sxs-lookup"><span data-stu-id="b57be-109">-or-</span></span>  
  
-   <span data-ttu-id="b57be-110">Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b57be-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="b57be-111">No se puede heredar de una interfaz o clase base más restringido.</span><span class="sxs-lookup"><span data-stu-id="b57be-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57be-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b57be-112">See Also</span></span>  
 [<span data-ttu-id="b57be-113">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b57be-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="b57be-114">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b57be-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="b57be-115">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b57be-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="b57be-116">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b57be-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
