---
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588267"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="c07d1-102">Se produjeron errores al compilar los esquemas XML del proyecto</span><span class="sxs-lookup"><span data-stu-id="c07d1-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="c07d1-103">Se produjeron errores durante la compilación de los esquemas XML en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="c07d1-104">Por este motivo, IntelliSense XML no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c07d1-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="c07d1-105">Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="c07d1-106">Este error se produce cuando se agrega un archivo de esquema (.xsd) de XSD que está en conflicto con el esquema XSD existente establecida para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="c07d1-107">**Id. de error:** BC36810</span><span class="sxs-lookup"><span data-stu-id="c07d1-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c07d1-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c07d1-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c07d1-109">Haga doble clic en la advertencia en el **lista de errores** ventana.</span><span class="sxs-lookup"><span data-stu-id="c07d1-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="c07d1-110">Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="c07d1-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="c07d1-111">Corrija el error en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="c07d1-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="c07d1-112">Asegúrese de que todos los necesarios se incluyen archivos de esquema (.xsd) de XSD en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="c07d1-113">Debe hacer clic en **mostrar todos los archivos** en el **proyecto** archivos de menú para ver su .xsd en **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c07d1-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="c07d1-114">Haga clic en un archivo .xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="c07d1-115">Si usas el Asistente de XML a esquema, este error puede producirse si deduce esquemas más de una vez desde el mismo origen.</span><span class="sxs-lookup"><span data-stu-id="c07d1-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="c07d1-116">En este caso, puede quitar los archivos de esquema XSD existentes desde el proyecto, agregue un nuevo XML en la plantilla de elementos de esquema y, a continuación, escriba el XML en el Asistente para esquemas con todos los orígenes XML aplicables para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c07d1-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="c07d1-117">Si no se identifica ningún error en el esquema XSD, el compilador XML no puede tener información suficiente para proporcionar un mensaje de error detallado.</span><span class="sxs-lookup"><span data-stu-id="c07d1-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="c07d1-118">Es posible que pueda obtener información más detallada del error si está seguro de que los espacios de nombres XML para los archivos .xsd incluyan en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c07d1-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c07d1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c07d1-119">See Also</span></span>  
 [<span data-ttu-id="c07d1-120">Lista de errores (Ventana)</span><span class="sxs-lookup"><span data-stu-id="c07d1-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)  
 [<span data-ttu-id="c07d1-121">XML</span><span class="sxs-lookup"><span data-stu-id="c07d1-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
