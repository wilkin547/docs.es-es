---
title: Crear el modelo de objetos
ms.date: 03/30/2017
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
ms.openlocfilehash: 7724d6e75b350e5c57f090d42ef1f49c4d3593b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032453"
---
# <a name="creating-the-object-model"></a><span data-ttu-id="1e0b5-102">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="1e0b5-102">Creating the Object Model</span></span>
<span data-ttu-id="1e0b5-103">Puede crear un modelo de objetos a partir de una base de datos existente y utilizar el modelo en su estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="1e0b5-104">También puede personalizar muchos aspectos del modelo y su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="1e0b5-105">Si utiliza Visual Studio, puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para crear un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e0b5-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1e0b5-106">In This Section</span></span>  
 [<span data-ttu-id="1e0b5-107">Cómo: Generación del modelo de objetos en Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="1e0b5-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="1e0b5-108">Describe cómo utilizar la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="1e0b5-109">También proporciona un vínculo a la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para usuarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1e0b5-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="1e0b5-110">Cómo: Generar el modelo de objetos como un archivo externo</span><span class="sxs-lookup"><span data-stu-id="1e0b5-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="1e0b5-111">Describe cómo generar un archivo de asignación externa en lugar de utilizar la asignación basada en atributos.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="1e0b5-112">Cómo: Generar código personalizado modificando un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="1e0b5-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="1e0b5-113">Describe cómo generar en Visual Basic o C# código desde un archivo de metadatos DBML.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="1e0b5-114">Cómo: Validar archivos DBML y asignación externa</span><span class="sxs-lookup"><span data-stu-id="1e0b5-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="1e0b5-115">Describe cómo validar archivos de asignación que se han modificado (avanzado).</span><span class="sxs-lookup"><span data-stu-id="1e0b5-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="1e0b5-116">Cómo: Serializar entidades</span><span class="sxs-lookup"><span data-stu-id="1e0b5-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="1e0b5-117">Describe cómo agregar los atributos adecuados para hacer que las entidades sean serializables.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="1e0b5-118">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="1e0b5-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="1e0b5-119">Describe cómo utilizar el editor de código para escribir su propio código de asignación o personalizar código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e0b5-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1e0b5-120">Related Sections</span></span>  
 [<span data-ttu-id="1e0b5-121">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1e0b5-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="1e0b5-122">Proporciona detalles sobre el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="1e0b5-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="1e0b5-123">Pasos habituales para usar LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1e0b5-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="1e0b5-124">Explica los pasos que normalmente son necesarios para implementar una aplicación [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0b5-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
