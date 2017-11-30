---
title: No se puede hacer referencia a &#39; &lt;nombre&gt;&#39; porque es un miembro del campo de tipo de valor &#39;&lt; nombre&gt;&#39; de la clase &#39;&lt; ClassName&gt;&#39; que tiene &#39; System.MarshalByRefObject &#39; como una clase base
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords: BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="2ed58-102">No se puede hacer referencia a &#39; &lt;nombre&gt;&#39; porque es un miembro del campo de tipo de valor &#39;&lt; nombre&gt;&#39; de la clase &#39;&lt; ClassName&gt;&#39; que tiene &#39; System.MarshalByRefObject &#39; como una clase base</span><span class="sxs-lookup"><span data-stu-id="2ed58-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="2ed58-103">La `System.MarshalByRefObject` clase permite a las aplicaciones que admiten el acceso remoto a los objetos en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ed58-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="2ed58-104">Los tipos deben heredar de la `MarshalByRejectObject` clase cuando el tipo se utiliza en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ed58-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="2ed58-105">No se debe copiar el estado del objeto porque los miembros del objeto no se puede usar fuera del dominio de aplicación en el que se crearon.</span><span class="sxs-lookup"><span data-stu-id="2ed58-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="2ed58-106">**Id. de error:** BC30310</span><span class="sxs-lookup"><span data-stu-id="2ed58-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ed58-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2ed58-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="2ed58-108">Compruebe la referencia para asegurarse de que el miembro que se hace referencia es válido.</span><span class="sxs-lookup"><span data-stu-id="2ed58-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="2ed58-109">Califique explícitamente el miembro con el `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="2ed58-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed58-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ed58-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="2ed58-111">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ed58-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
