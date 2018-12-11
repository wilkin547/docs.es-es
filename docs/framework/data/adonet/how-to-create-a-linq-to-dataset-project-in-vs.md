---
title: Crear un proyecto de LINQ to DataSet en Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154039"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Procedimiento Crear un proyecto de LINQ to DataSet en Visual Studio

Los distintos tipos de proyectos LINQ requieren determinadas referencias a ensamblados y espacios de nombres importados (Visual Basic) o [mediante](../../../csharp/language-reference/keywords/using-directive.md) directivas (C#). El requisito mínimo para LINQ es una referencia a *System.Core.dll* y un `using` directiva <xref:System.Linq>.

Estos requisitos se proporcionan de forma predeterminada si crea un nuevo proyecto de aplicación de consola de C# en Visual Studio 2017. Si está actualizando un proyecto desde una versión anterior de Visual Studio, es posible que deba proporcionar estas referencias relacionadas con LINQ de forma manual.

LINQ a conjunto de datos requiere dos referencias adicionales a *System.Data.dll* y *System.Data.DataSetExtensions.dll*.

> [!NOTE]
> Si va a crear desde un símbolo del sistema, deben hacer referencia manualmente las DLL relacionadas con LINQ en *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Para habilitar la funcionalidad LINQ to DataSet

Siga estos pasos para habilitar LINQ a la funcionalidad del conjunto de datos en un proyecto existente.

1. Agregue referencias a **System.Core**, **System.Data**, y **System.Data.DataSetExtensions**.

   En **el Explorador de soluciones**, haga doble clic en el **referencias** nodo y seleccione **Agregar referencia**. En el **Administrador de referencias** cuadro de diálogo, seleccione **System.Core**, **System.Data**, y **System.Data.DataSetExtensions**. Seleccione **Aceptar**.

1. Agregar [mediante](../../../csharp/language-reference/keywords/using-directive.md) directivas (o [instrucciones Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) en Visual Basic) para **System.Data** y **System.Linq**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Opcionalmente, agregue un `using` directiva (o `Imports` instrucción) para **System.Data.Common** o **System.Data.SqlClient**, dependiendo de cómo conectarse a la base de datos.

## <a name="see-also"></a>Vea también

- [Empezar a trabajar con LINQ to DataSet](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
