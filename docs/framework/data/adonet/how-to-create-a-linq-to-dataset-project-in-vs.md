---
title: Creación de un proyecto de LINQ to DataSet en Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783777"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Procedimiento Creación de un proyecto de LINQ to DataSet en Visual Studio

Los diferentes tipos de proyectos de LINQ requieren ciertas referencias de ensamblado y espacios de nombres importados (Visual Basic) o [mediante](../../../csharp/language-reference/keywords/using-directive.md) directivas (C#). El requisito mínimo para LINQ es una referencia a *System. Core. dll* y una `using` Directiva para <xref:System.Linq>.

Estos requisitos se proporcionan de forma predeterminada si crea un nuevo C# proyecto de aplicación de consola en Visual Studio 2017. Si va a actualizar un proyecto de una versión anterior de Visual Studio, es posible que tenga que proporcionar estas referencias relacionadas con LINQ de forma manual.

LINQ to DataSet requiere dos referencias adicionales a *System. Data. dll* y *System. Data. DataSetExtensions. dll*.

> [!NOTE]
> Si va a compilar desde un símbolo del sistema, debe hacer referencia manualmente a las DLL relacionadas con LINQ en *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Para habilitar la funcionalidad LINQ to DataSet

Siga estos pasos para habilitar LINQ to DataSet funcionalidad en un proyecto existente.

1. Agregue referencias a **System. Core**, **System. Data**y **System. Data. DataSetExtensions**.

   En **Explorador de soluciones**, haga clic con el botón secundario en el nodo **referencias** y seleccione **Agregar referencia**. En el cuadro de diálogo **Administrador de referencias** , seleccione **System. Core**, **System. Data**y **System. Data. DataSetExtensions**. Seleccione **Aceptar**.

1. Agregue directivas [using](../../../csharp/language-reference/keywords/using-directive.md) (o [instrucciones Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) en Visual Basic) para **System. Data** y **System. Linq**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Opcionalmente, agregue una `using` Directiva (o `Imports` instrucción) para **System. Data. Common** o **System. Data. SqlClient**, dependiendo de cómo se conecte a la base de datos.

## <a name="see-also"></a>Vea también

- [Introducción a LINQ to DataSet](getting-started-linq-to-dataset.md)
