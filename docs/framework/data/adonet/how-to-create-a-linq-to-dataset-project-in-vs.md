---
description: 'Más información acerca de cómo: crear un proyecto de LINQ to DataSet en Visual Studio'
title: Creación de un proyecto de LINQ to DataSet en Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 4ab626ddaa27780759df95462faac366be8beeff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723834"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="21315-103">Cómo: crear un proyecto de LINQ to DataSet en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21315-103">How to: Create a LINQ to DataSet project in Visual Studio</span></span>

<span data-ttu-id="21315-104">Los diferentes tipos de proyectos de LINQ requieren ciertas referencias de ensamblado y espacios de nombres importados (Visual Basic) o directivas [using](../../../csharp/language-reference/keywords/using-directive.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="21315-104">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="21315-105">El requisito mínimo para LINQ es una referencia a *System.Core.dll* y una `using` Directiva para <xref:System.Linq> .</span><span class="sxs-lookup"><span data-stu-id="21315-105">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="21315-106">Estos requisitos se proporcionan de forma predeterminada si crea un nuevo proyecto de aplicación de consola de C# en Visual Studio 2017 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="21315-106">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017 or a later version.</span></span> <span data-ttu-id="21315-107">Si va a actualizar un proyecto de una versión anterior de Visual Studio, es posible que tenga que proporcionar estas referencias relacionadas con LINQ de forma manual.</span><span class="sxs-lookup"><span data-stu-id="21315-107">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="21315-108">LINQ to DataSet requiere dos referencias adicionales a *System.Data.dll* y *System.Data.DataSetExtensions.dll*.</span><span class="sxs-lookup"><span data-stu-id="21315-108">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="21315-109">Si va a compilar desde un símbolo del sistema, debe hacer referencia manualmente a las DLL relacionadas con LINQ en *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="21315-109">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="21315-110">Para habilitar la funcionalidad LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="21315-110">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="21315-111">Siga estos pasos para habilitar LINQ to DataSet funcionalidad en un proyecto existente.</span><span class="sxs-lookup"><span data-stu-id="21315-111">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="21315-112">Agregue referencias a **System. Core**, **System. Data** y **System. Data. DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="21315-112">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="21315-113">En **Explorador de soluciones**, haga clic con el botón secundario en el nodo **referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="21315-113">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="21315-114">En el cuadro de diálogo **Administrador de referencias** , seleccione **System. Core**, **System. Data** y **System. Data. DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="21315-114">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="21315-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21315-115">Select **OK**.</span></span>

1. <span data-ttu-id="21315-116">Agregue directivas [using](../../../csharp/language-reference/keywords/using-directive.md) (o [instrucciones Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) en Visual Basic) para **System. Data** y **System. Linq**.</span><span class="sxs-lookup"><span data-stu-id="21315-116">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="21315-117">Opcionalmente, agregue una `using` Directiva (o `Imports` instrucción) para **System. Data. Common** o **System. Data. SqlClient**, dependiendo de cómo se conecte a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="21315-117">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="21315-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="21315-118">See also</span></span>

- [<span data-ttu-id="21315-119">Introducción a LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="21315-119">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
