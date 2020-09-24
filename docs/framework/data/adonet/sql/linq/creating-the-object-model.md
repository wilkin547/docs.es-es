---
title: Crear el modelo de objetos
ms.date: 03/30/2017
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
ms.openlocfilehash: 2191c29c0b2e56f9fdf7983bf96d2494867f318b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164368"
---
# <a name="creating-the-object-model"></a><span data-ttu-id="8dcca-102">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="8dcca-102">Creating the Object Model</span></span>

<span data-ttu-id="8dcca-103">Puede crear un modelo de objetos a partir de una base de datos existente y utilizar el modelo en su estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8dcca-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="8dcca-104">También puede personalizar muchos aspectos del modelo y su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8dcca-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="8dcca-105">Si usa Visual Studio, puede usar la Object Relational Designer para crear el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8dcca-105">If you are using Visual Studio, you can use the Object Relational Designer to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dcca-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8dcca-106">In This Section</span></span>  

 [<span data-ttu-id="8dcca-107">Cómo: Generación del modelo de objetos en Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="8dcca-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="8dcca-108">Describe cómo utilizar la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="8dcca-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="8dcca-109">También proporciona un vínculo a la Object Relational Designer para los usuarios de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8dcca-109">Also provides a link to the Object Relational Designer for Visual Studio users</span></span>  
  
 [<span data-ttu-id="8dcca-110">Procedimiento para generar el modelo de objetos como un archivo externo</span><span class="sxs-lookup"><span data-stu-id="8dcca-110">How to: Generate the Object Model as an External File</span></span>](how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="8dcca-111">Describe cómo generar un archivo de asignación externa en lugar de utilizar la asignación basada en atributos.</span><span class="sxs-lookup"><span data-stu-id="8dcca-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="8dcca-112">Procedimiento para generar código personalizado mediante la modificación de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="8dcca-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="8dcca-113">Describe cómo generar código de Visual Basic o C# a partir de un archivo de metadatos DBML.</span><span class="sxs-lookup"><span data-stu-id="8dcca-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="8dcca-114">Procedimiento para validar archivos DBML y de asignación externa</span><span class="sxs-lookup"><span data-stu-id="8dcca-114">How to: Validate DBML and External Mapping Files</span></span>](how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="8dcca-115">Describe cómo validar archivos de asignación que se han modificado (avanzado).</span><span class="sxs-lookup"><span data-stu-id="8dcca-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="8dcca-116">Procedimiento para serializar entidades</span><span class="sxs-lookup"><span data-stu-id="8dcca-116">How to: Make Entities Serializable</span></span>](how-to-make-entities-serializable.md)  
 <span data-ttu-id="8dcca-117">Describe cómo agregar los atributos adecuados para hacer que las entidades sean serializables.</span><span class="sxs-lookup"><span data-stu-id="8dcca-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="8dcca-118">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="8dcca-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="8dcca-119">Describe cómo utilizar el editor de código para escribir su propio código de asignación o personalizar código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8dcca-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8dcca-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8dcca-120">Related Sections</span></span>  

 [<span data-ttu-id="8dcca-121">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8dcca-121">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)  
 <span data-ttu-id="8dcca-122">Proporciona detalles sobre el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8dcca-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="8dcca-123">Pasos habituales para usar LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8dcca-123">Typical Steps for Using LINQ to SQL</span></span>](typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="8dcca-124">Explica los pasos que normalmente son necesarios para implementar una aplicación [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dcca-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
