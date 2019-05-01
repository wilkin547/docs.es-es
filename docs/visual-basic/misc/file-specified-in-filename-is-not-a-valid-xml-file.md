---
title: El archivo especificado en Nombre de archivo no es un archivo XML válido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 89499b07e767bd0b3a777db4e5155f64a4357f0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052318"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="2f17e-102">El archivo especificado en Nombre de archivo no es un archivo XML válido</span><span class="sxs-lookup"><span data-stu-id="2f17e-102">File specified in FileName is not a valid XML file</span></span>

<span data-ttu-id="2f17e-103">El nombre de archivo proporcionado no es un archivo XML válido.</span><span class="sxs-lookup"><span data-stu-id="2f17e-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="2f17e-104">Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="2f17e-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="2f17e-105">Los esquemas XSD son el método preferido para especificar gramáticas XML en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f17e-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="2f17e-106">En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="2f17e-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="2f17e-107">El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="2f17e-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="2f17e-108">Sin embargo, en Visual Studio 2012, el diseñador para crear y editar conjuntos de datos con tipo es el **Diseñador de Dataset**.</span><span class="sxs-lookup"><span data-stu-id="2f17e-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="2f17e-109">Para obtener más información, consulte [crear y editar conjuntos de datos con tipo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2f17e-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2f17e-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2f17e-110">To correct this error</span></span>

- <span data-ttu-id="2f17e-111">Compruebe que está proporcionando el nombre de archivo correcto.</span><span class="sxs-lookup"><span data-stu-id="2f17e-111">Check that you are supplying the correct file name.</span></span>

- <span data-ttu-id="2f17e-112">Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**.</span><span class="sxs-lookup"><span data-stu-id="2f17e-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="2f17e-113">En el menú **XML** , haga clic en **Validar datos XML**.</span><span class="sxs-lookup"><span data-stu-id="2f17e-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="2f17e-114">Los errores se muestran en la ventana **Lista de tareas**.</span><span class="sxs-lookup"><span data-stu-id="2f17e-114">Errors are displayed in the **Task List**.</span></span>

- <span data-ttu-id="2f17e-115">Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="2f17e-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f17e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f17e-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="2f17e-117">Cómo: Analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="2f17e-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)