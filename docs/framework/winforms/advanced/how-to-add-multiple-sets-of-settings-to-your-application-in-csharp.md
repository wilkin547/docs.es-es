---
title: Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 9a4913f635204aac2214d97225c7b8147c6fe9ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768555"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="034de-102">Cómo Agregar varios conjuntos de configuración de la aplicación en C\#</span><span class="sxs-lookup"><span data-stu-id="034de-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="034de-103">En algunos casos, puede tener varios conjuntos de configuración en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="034de-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="034de-104">Por ejemplo, si está desarrollando una aplicación donde se espera un determinado grupo de valores que cambian con frecuencia, sería conveniente separar todos en un único archivo para que se puede reemplazar el archivo de manera global, que no afecta a otras opciones.</span><span class="sxs-lookup"><span data-stu-id="034de-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="034de-105">Visual Studio permite agregar varios conjuntos de configuración al proyecto.</span><span class="sxs-lookup"><span data-stu-id="034de-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="034de-106">Pueden acceder a través del objeto Properties.Settings conjuntos adicionales de configuración.</span><span class="sxs-lookup"><span data-stu-id="034de-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="034de-107">Para agregar un conjunto adicional de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="034de-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1. <span data-ttu-id="034de-108">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="034de-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="034de-109">Se abre el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="034de-109">The **Add New Item** dialog box opens.</span></span>  
  
2. <span data-ttu-id="034de-110">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivoConfiguración**, escriba un nombre para el archivo y haga clic en **agregar** para agregar un nuevo archivo de configuración a la solución.</span><span class="sxs-lookup"><span data-stu-id="034de-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3. <span data-ttu-id="034de-111">En **el Explorador de soluciones**, arrastre el nuevo archivo de configuración en el **propiedades** carpeta.</span><span class="sxs-lookup"><span data-stu-id="034de-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="034de-112">Esto permite que la nueva configuración esté disponible en el código.</span><span class="sxs-lookup"><span data-stu-id="034de-112">This allows your new settings to be available in code.</span></span>  
  
4. <span data-ttu-id="034de-113">Agregar y usar la configuración de este archivo como lo haría con cualquier otro archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="034de-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="034de-114">Puede tener acceso a este grupo de configuración a través del objeto Properties.Settings.</span><span class="sxs-lookup"><span data-stu-id="034de-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034de-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="034de-115">See also</span></span>

- [<span data-ttu-id="034de-116">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="034de-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="034de-117">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="034de-117">Application Settings Overview</span></span>](application-settings-overview.md)
