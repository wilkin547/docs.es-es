---
title: "El archivo especificado en Nombre de archivo no es un archivo XML válido"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3275608a1871ac981eb5b3aa39f0be6ab4e758e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="484b3-102">El archivo especificado en Nombre de archivo no es un archivo XML válido</span><span class="sxs-lookup"><span data-stu-id="484b3-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="484b3-103">El nombre de archivo proporcionado no es un archivo XML válido.</span><span class="sxs-lookup"><span data-stu-id="484b3-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="484b3-104">Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="484b3-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="484b3-105">Los esquemas XSD son el método preferido para especificar gramáticas XML en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="484b3-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="484b3-106">En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="484b3-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="484b3-107">El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="484b3-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="484b3-108">Sin embargo, en [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)], el diseñador para crear y editar conjuntos de datos es el **Diseñador de Dataset**.</span><span class="sxs-lookup"><span data-stu-id="484b3-108">However, in [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="484b3-109">Para obtener más información, consulte [crear y editar conjuntos de datos con tipo](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="484b3-109">For more information, see [Creating and Editing Typed Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="484b3-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="484b3-110">To correct this error</span></span>  
  
-   <span data-ttu-id="484b3-111">Compruebe que está proporcionando el nombre de archivo correcto.</span><span class="sxs-lookup"><span data-stu-id="484b3-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="484b3-112">Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**.</span><span class="sxs-lookup"><span data-stu-id="484b3-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="484b3-113">En el menú **XML** , haga clic en **Validar datos XML**.</span><span class="sxs-lookup"><span data-stu-id="484b3-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="484b3-114">Los errores se muestran en la ventana **Lista de tareas**.</span><span class="sxs-lookup"><span data-stu-id="484b3-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="484b3-115">Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="484b3-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484b3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="484b3-116">See Also</span></span>  
 <xref:System.Xml>  
 [<span data-ttu-id="484b3-117">Analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="484b3-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
