---
title: Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040125"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="d8ef8-102">Cómo Agregar varios conjuntos de valores de configuración a la aplicación en C\#</span><span class="sxs-lookup"><span data-stu-id="d8ef8-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="d8ef8-103">En algunos casos, es posible que desee tener varios conjuntos de valores de configuración en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="d8ef8-104">Por ejemplo, si está desarrollando una aplicación en la que se espera que un grupo determinado de valores de configuración cambie con frecuencia, puede ser aconsejable separarlos en un único archivo para que el archivo se pueda reemplazar de forma mayorista y no afecte a otros valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="d8ef8-105">Visual Studio permite agregar varios conjuntos de valores de configuración al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="d8ef8-106">Se puede obtener acceso a conjuntos de configuración adicionales a `Properties.Settings` través del objeto.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-106">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="d8ef8-107">Agregar un conjunto de valores adicional</span><span class="sxs-lookup"><span data-stu-id="d8ef8-107">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="d8ef8-108">En Visual Studio, en el menú **proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-108">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="d8ef8-109">Se abre el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-109">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="d8ef8-110">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **archivo de configuración**, escriba un nombre para el archivo y haga clic en **Agregar** para agregar un nuevo archivo de configuración a la solución.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-110">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="d8ef8-111">En **Explorador de soluciones**, arrastre el nuevo archivo de configuración a la carpeta **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="d8ef8-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="d8ef8-112">Esto permite que la nueva configuración esté disponible en el código.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-112">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="d8ef8-113">Agregue y use la configuración de este archivo como lo haría con cualquier otro archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="d8ef8-114">Puede tener acceso a este grupo de configuración a `Properties.Settings` través del objeto.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-114">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8ef8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8ef8-115">See also</span></span>

- [<span data-ttu-id="d8ef8-116">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="d8ef8-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="d8ef8-117">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d8ef8-117">Application Settings Overview</span></span>](application-settings-overview.md)
