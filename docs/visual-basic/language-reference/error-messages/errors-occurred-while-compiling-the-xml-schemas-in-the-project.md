---
description: 'Más información acerca de: BC36810: se produjeron errores al compilar los esquemas XML en el proyecto'
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 78e88208c0d3df12e7bad8ab46b1d91bce559923
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796488"
---
# <a name="bc36810-errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="19e0c-103">BC36810: se produjeron errores al compilar los esquemas XML en el proyecto</span><span class="sxs-lookup"><span data-stu-id="19e0c-103">BC36810: Errors occurred while compiling the XML schemas in the project</span></span>

<span data-ttu-id="19e0c-104">Se produjeron errores al compilar los esquemas XML en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-104">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="19e0c-105">Por ello, XML IntelliSense no está disponible.</span><span class="sxs-lookup"><span data-stu-id="19e0c-105">Because of this, XML IntelliSense is not available.</span></span>

 <span data-ttu-id="19e0c-106">Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-106">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="19e0c-107">Este error se produce cuando se agrega un archivo de esquema XSD (. xsd) que entra en conflicto con el conjunto de esquemas XSD existente para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-107">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>

 <span data-ttu-id="19e0c-108">**Identificador de error:** BC36810</span><span class="sxs-lookup"><span data-stu-id="19e0c-108">**Error ID:** BC36810</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="19e0c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="19e0c-109">To correct this error</span></span>

- <span data-ttu-id="19e0c-110">Haga doble clic en la advertencia en la ventana **lista de errores** .</span><span class="sxs-lookup"><span data-stu-id="19e0c-110">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="19e0c-111">Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="19e0c-111">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="19e0c-112">Corrija el error en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="19e0c-112">Correct the error in the XSD schema.</span></span>

- <span data-ttu-id="19e0c-113">Asegúrese de que todos los archivos de esquema XSD (. xsd) necesarios se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-113">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="19e0c-114">Es posible que tenga que hacer clic en **Mostrar todos los archivos** en el menú **proyecto** para ver los archivos. xsd en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="19e0c-114">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="19e0c-115">Haga clic con el botón secundario en un archivo. xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-115">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>

- <span data-ttu-id="19e0c-116">Si usa el Asistente de XML a esquema, este error puede producirse si se infieren esquemas más de una vez desde el mismo origen.</span><span class="sxs-lookup"><span data-stu-id="19e0c-116">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="19e0c-117">En este caso, puede quitar los archivos de esquema XSD existentes del proyecto, agregar un nuevo XML a la plantilla de elemento de esquema y, a continuación, proporcionar el Asistente de XML a esquema con todos los orígenes XML aplicables para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="19e0c-117">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>

- <span data-ttu-id="19e0c-118">Si no se identifica ningún error en el esquema XSD, es posible que el compilador XML no tenga suficiente información para proporcionar un mensaje de error detallado.</span><span class="sxs-lookup"><span data-stu-id="19e0c-118">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="19e0c-119">Es posible que pueda obtener información más detallada del error si se asegura de que los espacios de nombres XML para los archivos. xsd incluidos en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML establecido en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="19e0c-119">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="19e0c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="19e0c-120">See also</span></span>

- [<span data-ttu-id="19e0c-121">Lista de errores ventana</span><span class="sxs-lookup"><span data-stu-id="19e0c-121">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="19e0c-122">XML</span><span class="sxs-lookup"><span data-stu-id="19e0c-122">XML</span></span>](../../programming-guide/language-features/xml/index.md)
