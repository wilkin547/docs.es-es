---
title: Acceso a los datos de usuario (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- domain names [Visual Basic], retrieving
- data [Visual Basic], accessing user data
- My.User object [Visual Basic], tasks
- user data [Visual Basic], domain
- user names [Visual Basic], retrieving
- user data [Visual Basic], accessing
- login names [Visual Basic]
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92c0b97059896e86d54069b637c9956cac9d10e8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="1fb51-102">Acceso a los datos de usuario (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fb51-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="1fb51-103">Esta sección contiene temas que tratan del objeto `My.User` y de las tareas que se pueden realizar con él.</span><span class="sxs-lookup"><span data-stu-id="1fb51-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="1fb51-104">El objeto `My.User` proporciona acceso a información sobre los usuarios que han iniciado la sesión devolviendo un objeto que implementa la interfaz <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="1fb51-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="1fb51-105">Tareas</span><span class="sxs-lookup"><span data-stu-id="1fb51-105">Tasks</span></span>  
  
|<span data-ttu-id="1fb51-106">Para</span><span class="sxs-lookup"><span data-stu-id="1fb51-106">To</span></span>|<span data-ttu-id="1fb51-107">Vea</span><span class="sxs-lookup"><span data-stu-id="1fb51-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="1fb51-108">Obtener el nombre de inicio de sesión del usuario</span><span class="sxs-lookup"><span data-stu-id="1fb51-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="1fb51-109">Obtener el nombre de dominio del usuario si la aplicación usa la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1fb51-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="1fb51-110">Determinar el rol del usuario</span><span class="sxs-lookup"><span data-stu-id="1fb51-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="1fb51-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fb51-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>
