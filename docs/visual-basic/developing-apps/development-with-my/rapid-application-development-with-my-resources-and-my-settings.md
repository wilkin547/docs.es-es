---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: fd1ec25582e919b84235502f5921edfbc6e1dade
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990208"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="6bfd8-102">Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bfd8-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="6bfd8-103">El objeto `My.Resources` da acceso a los recursos de la aplicación y permite recuperar recursos de la aplicación dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="6bfd8-104">Recuperar recursos</span><span class="sxs-lookup"><span data-stu-id="6bfd8-104">Retrieving Resources</span></span>  

 <span data-ttu-id="6bfd8-105">Con el objeto `My.Resources` se pueden recuperar una serie de recursos, como archivos de audio, iconos, imágenes y cadenas.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="6bfd8-106">Por ejemplo, permite acceder a los archivos de recursos específicos de la referencia cultural de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="6bfd8-107">En el siguiente ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="6bfd8-108">El objeto `My.Resources` expone solo recursos globales.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="6bfd8-109">No da acceso a los archivos de recursos asociados a los formularios.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="6bfd8-110">Acceda a los recursos del formulario desde el formulario.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-110">Access the form resources from the form.</span></span>  
  
 <span data-ttu-id="6bfd8-111">De forma similar, el objeto `My.Settings` da acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bfd8-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="6bfd8-112">Para más información, vea [My.Resources Object](../../language-reference/objects/my-resources-object.md) y [My.Settings Object](../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="6bfd8-112">For more information, see [My.Resources Object](../../language-reference/objects/my-resources-object.md) and [My.Settings Object](../../language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bfd8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bfd8-113">See also</span></span>

- [<span data-ttu-id="6bfd8-114">My.Resources (objeto)</span><span class="sxs-lookup"><span data-stu-id="6bfd8-114">My.Resources Object</span></span>](../../language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="6bfd8-115">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="6bfd8-115">My.Settings Object</span></span>](../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="6bfd8-116">Acceso a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6bfd8-116">Accessing Application Settings</span></span>](../programming/app-settings/index.md)
