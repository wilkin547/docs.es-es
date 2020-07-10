---
title: Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#
description: Obtenga información sobre cómo agregar varios conjuntos de valores de Windows Forms a la aplicación en C# mediante Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173450"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="e07ea-103">Cómo: agregar varios conjuntos de valores a la aplicación en C\#</span><span class="sxs-lookup"><span data-stu-id="e07ea-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="e07ea-104">En algunos casos, es posible que desee tener varios conjuntos de valores de configuración en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e07ea-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="e07ea-105">Por ejemplo, si está desarrollando una aplicación en la que se espera que un grupo determinado de valores de configuración cambie con frecuencia, puede ser aconsejable separarlos en un único archivo para que el archivo se pueda reemplazar de forma mayorista y no afecte a otros valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="e07ea-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="e07ea-106">Visual Studio permite agregar varios conjuntos de valores de configuración al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e07ea-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="e07ea-107">Se puede obtener acceso a conjuntos de configuración adicionales a través del `Properties.Settings` objeto.</span><span class="sxs-lookup"><span data-stu-id="e07ea-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="e07ea-108">Agregar un conjunto de valores adicional</span><span class="sxs-lookup"><span data-stu-id="e07ea-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="e07ea-109">En Visual Studio, en el menú **proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e07ea-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="e07ea-110">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e07ea-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="e07ea-111">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **archivo de configuración**, escriba un nombre para el archivo y haga clic en **Agregar** para agregar un nuevo archivo de configuración a la solución.</span><span class="sxs-lookup"><span data-stu-id="e07ea-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="e07ea-112">En **Explorador de soluciones**, arrastre el nuevo archivo de configuración a la carpeta **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="e07ea-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="e07ea-113">Esto permite que la nueva configuración esté disponible en el código.</span><span class="sxs-lookup"><span data-stu-id="e07ea-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="e07ea-114">Agregue y use la configuración de este archivo como lo haría con cualquier otro archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e07ea-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="e07ea-115">Puede tener acceso a este grupo de configuración a través del `Properties.Settings` objeto.</span><span class="sxs-lookup"><span data-stu-id="e07ea-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="e07ea-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e07ea-116">See also</span></span>

- [<span data-ttu-id="e07ea-117">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="e07ea-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e07ea-118">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e07ea-118">Application Settings Overview</span></span>](application-settings-overview.md)
