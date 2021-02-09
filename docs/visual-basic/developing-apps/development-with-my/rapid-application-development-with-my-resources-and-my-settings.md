---
description: 'Más información acerca de: Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)'
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 38846b3a6ac273306f588ad8b043d7f35f7230a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797931"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="57ce5-103">Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57ce5-103">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="57ce5-104">El objeto `My.Resources` da acceso a los recursos de la aplicación y permite recuperar recursos de la aplicación dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="57ce5-104">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="57ce5-105">Recuperar recursos</span><span class="sxs-lookup"><span data-stu-id="57ce5-105">Retrieving Resources</span></span>  

 <span data-ttu-id="57ce5-106">Con el objeto `My.Resources` se pueden recuperar una serie de recursos, como archivos de audio, iconos, imágenes y cadenas.</span><span class="sxs-lookup"><span data-stu-id="57ce5-106">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="57ce5-107">Por ejemplo, permite acceder a los archivos de recursos específicos de la referencia cultural de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57ce5-107">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="57ce5-108">En el siguiente ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57ce5-108">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="57ce5-109">El objeto `My.Resources` expone solo recursos globales.</span><span class="sxs-lookup"><span data-stu-id="57ce5-109">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="57ce5-110">No da acceso a los archivos de recursos asociados a los formularios.</span><span class="sxs-lookup"><span data-stu-id="57ce5-110">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="57ce5-111">Acceda a los recursos del formulario desde el formulario.</span><span class="sxs-lookup"><span data-stu-id="57ce5-111">Access the form resources from the form.</span></span>  
  
 <span data-ttu-id="57ce5-112">De forma similar, el objeto `My.Settings` da acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57ce5-112">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="57ce5-113">Para más información, vea [My.Resources Object](../../language-reference/objects/my-resources-object.md) y [My.Settings Object](../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="57ce5-113">For more information, see [My.Resources Object](../../language-reference/objects/my-resources-object.md) and [My.Settings Object](../../language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ce5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="57ce5-114">See also</span></span>

- [<span data-ttu-id="57ce5-115">My.Resources (objeto)</span><span class="sxs-lookup"><span data-stu-id="57ce5-115">My.Resources Object</span></span>](../../language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="57ce5-116">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="57ce5-116">My.Settings Object</span></span>](../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="57ce5-117">Acceso a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="57ce5-117">Accessing Application Settings</span></span>](../programming/app-settings/index.md)
