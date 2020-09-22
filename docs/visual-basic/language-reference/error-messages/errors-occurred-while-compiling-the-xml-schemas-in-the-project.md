---
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 17c31301e28c757954e72ba103254f038905671f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874351"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="8c8b2-102">Se produjeron errores al compilar los esquemas XML del proyecto</span><span class="sxs-lookup"><span data-stu-id="8c8b2-102">Errors occurred while compiling the XML schemas in the project</span></span>

<span data-ttu-id="8c8b2-103">Se produjeron errores al compilar los esquemas XML en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="8c8b2-104">Por ello, XML IntelliSense no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="8c8b2-105">Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="8c8b2-106">Este error se produce cuando se agrega un archivo de esquema XSD (. xsd) que entra en conflicto con el conjunto de esquemas XSD existente para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="8c8b2-107">**Identificador de error:** BC36810</span><span class="sxs-lookup"><span data-stu-id="8c8b2-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c8b2-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8c8b2-108">To correct this error</span></span>  
  
- <span data-ttu-id="8c8b2-109">Haga doble clic en la advertencia en la ventana **lista de errores** .</span><span class="sxs-lookup"><span data-stu-id="8c8b2-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="8c8b2-110">Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="8c8b2-111">Corrija el error en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="8c8b2-112">Asegúrese de que todos los archivos de esquema XSD (. xsd) necesarios se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="8c8b2-113">Es posible que tenga que hacer clic en **Mostrar todos los archivos** en el menú **proyecto** para ver los archivos. xsd en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="8c8b2-114">Haga clic con el botón secundario en un archivo. xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="8c8b2-115">Si usa el Asistente de XML a esquema, este error puede producirse si se infieren esquemas más de una vez desde el mismo origen.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="8c8b2-116">En este caso, puede quitar los archivos de esquema XSD existentes del proyecto, agregar un nuevo XML a la plantilla de elemento de esquema y, a continuación, proporcionar el Asistente de XML a esquema con todos los orígenes XML aplicables para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="8c8b2-117">Si no se identifica ningún error en el esquema XSD, es posible que el compilador XML no tenga suficiente información para proporcionar un mensaje de error detallado.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="8c8b2-118">Es posible que pueda obtener información más detallada del error si se asegura de que los espacios de nombres XML para los archivos. xsd incluidos en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML establecido en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8c8b2-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8b2-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c8b2-119">See also</span></span>

- [<span data-ttu-id="8c8b2-120">Lista de errores ventana</span><span class="sxs-lookup"><span data-stu-id="8c8b2-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="8c8b2-121">XML</span><span class="sxs-lookup"><span data-stu-id="8c8b2-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
