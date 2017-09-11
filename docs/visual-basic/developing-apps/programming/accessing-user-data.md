---
title: Acceso a los datos de usuario (Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- domain names, retrieving
- data [Visual Basic], accessing user data
- My.User object, tasks
- user data, domain
- user names, retrieving
- user data, accessing
- login names
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 396ae45d26551c3a44a8a8fa6334a744508734a7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="5c2d9-102">Acceso a los datos de usuario (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c2d9-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="5c2d9-103">Esta sección contiene temas que tratan del objeto `My.User` y de las tareas que se pueden realizar con él.</span><span class="sxs-lookup"><span data-stu-id="5c2d9-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="5c2d9-104">El objeto `My.User` proporciona acceso a información sobre los usuarios que han iniciado la sesión devolviendo un objeto que implementa la interfaz <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="5c2d9-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5c2d9-105">Tareas</span><span class="sxs-lookup"><span data-stu-id="5c2d9-105">Tasks</span></span>  
  
|<span data-ttu-id="5c2d9-106">Para</span><span class="sxs-lookup"><span data-stu-id="5c2d9-106">To</span></span>|<span data-ttu-id="5c2d9-107">Vea</span><span class="sxs-lookup"><span data-stu-id="5c2d9-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="5c2d9-108">Obtener el nombre de inicio de sesión del usuario</span><span class="sxs-lookup"><span data-stu-id="5c2d9-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="5c2d9-109">Obtener el nombre de dominio del usuario si la aplicación usa la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5c2d9-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="5c2d9-110">Determinar el rol del usuario</span><span class="sxs-lookup"><span data-stu-id="5c2d9-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="5c2d9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c2d9-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>

