---
title: "&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; ya está implementado por la clase base &#39;&lt; nombredeclasebase&gt;&#39;. Reimplementación de &lt;tipo&gt; supone"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69884ed567e0046da5cf5c51b3e83e57e890d49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="ea628-103">&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; ya está implementado por la clase base &#39;&lt; nombredeclasebase&gt;&#39;.</span><span class="sxs-lookup"><span data-stu-id="ea628-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="ea628-104">Reimplementación de &lt;tipo&gt; supone</span><span class="sxs-lookup"><span data-stu-id="ea628-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="ea628-105">Una propiedad, procedimiento o evento en una clase derivada utiliza un `Implements` cláusula que especifica un miembro de interfaz que ya se ha implementado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="ea628-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="ea628-106">Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base.</span><span class="sxs-lookup"><span data-stu-id="ea628-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="ea628-107">Esto no es el mismo que reemplazar la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ea628-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="ea628-108">Para obtener más información, consulte [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ea628-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="ea628-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ea628-109">By default, this message is a warning.</span></span> <span data-ttu-id="ea628-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ea628-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ea628-111">**Id. de error:** BC42015</span><span class="sxs-lookup"><span data-stu-id="ea628-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea628-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ea628-112">To correct this error</span></span>  
  
-   <span data-ttu-id="ea628-113">Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="ea628-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="ea628-114">Código de la clase derivada tiene acceso al miembro nuevamente implementado a menos que utilice el `MyBase` palabra clave para tener acceso a la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ea628-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="ea628-115">Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.</span><span class="sxs-lookup"><span data-stu-id="ea628-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea628-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea628-116">See Also</span></span>  
 [<span data-ttu-id="ea628-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ea628-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
