---
title: "Cómo: Agregar varios conjuntos de valores de configuración a una aplicación en C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d9bd7d0721aae8691fdbca4d7b934f820666536
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="ec53c-102">Cómo: Agregar varios conjuntos de valores de configuración a una aplicación en C#</span><span class="sxs-lookup"><span data-stu-id="ec53c-102">How To: Add Multiple Sets of Settings To Your Application in C#</span></span> #
<span data-ttu-id="ec53c-103">En algunos casos, puede tener varios conjuntos de configuración en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec53c-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="ec53c-104">Por ejemplo, si está desarrollando una aplicación donde se espera un determinado grupo de valores que cambian con frecuencia, podría ser conveniente separarlos todos en un único archivo para que el archivo se puede reemplazar en su totalidad, no se ve afectada otros valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="ec53c-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="ec53c-105">Visual Studio permite agregar varios conjuntos de configuración para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ec53c-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="ec53c-106">Pueden tener acceso a conjuntos adicionales de configuración a través del objeto Properties.Settings.</span><span class="sxs-lookup"><span data-stu-id="ec53c-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="ec53c-107">Para agregar un conjunto adicional de configuración a la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec53c-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="ec53c-108">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="ec53c-109">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ec53c-110">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivo de configuración de**, escriba un nombre para el archivo y haga clic en **agregar** para agregar un nuevo archivo de configuración a la solución.</span><span class="sxs-lookup"><span data-stu-id="ec53c-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="ec53c-111">En **el Explorador de soluciones**, arrastre el nuevo archivo de configuración en el **propiedades** carpeta.</span><span class="sxs-lookup"><span data-stu-id="ec53c-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="ec53c-112">Esto permite que la nueva configuración esté disponible en el código.</span><span class="sxs-lookup"><span data-stu-id="ec53c-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="ec53c-113">Agregar y usar la configuración de este archivo como haría con cualquier otro archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ec53c-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="ec53c-114">Puede tener acceso a este grupo de configuración a través del objeto Properties.Settings.</span><span class="sxs-lookup"><span data-stu-id="ec53c-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec53c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec53c-115">See Also</span></span>  
 [<span data-ttu-id="ec53c-116">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="ec53c-116">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="ec53c-117">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec53c-117">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
