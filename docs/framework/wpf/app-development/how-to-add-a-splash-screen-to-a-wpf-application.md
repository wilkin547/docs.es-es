---
title: Cómo agregar una pantalla de presentación
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 39f53e21c40f036c65894b4f275cd5fb414999be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740449"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Cómo: Agregar una pantalla de presentación a una aplicación WPF

En este tema se muestra cómo agregar una ventana de inicio o una *pantalla de presentación*a una aplicación Windows Presentation Foundation (WPF).

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>Para agregar una imagen existente como pantalla de presentación

1. Cree o busque una imagen que desee usar para la pantalla de presentación. Puede usar cualquier formato de imagen que sea compatible con el componente de creación de imágenes de Windows (WIC). Por ejemplo, puede usar el formato BMP, GIF, JPEG, PNG o TIFF.

2. Agregue el archivo de imagen al proyecto de aplicación de WPF.

3. En **Explorador de soluciones**, seleccione la imagen.

4. En el ventana Propiedades, haga clic en la flecha desplegable de la propiedad **acción de compilación** .

5. Seleccione **SplashScreen** en la lista desplegable.

6. Presione **F5** para compilar y ejecutar la aplicación.

     La imagen de la pantalla de presentación aparece en el centro de la pantalla y, a continuación, se atenúa cuando aparece la ventana de la aplicación principal.

## <a name="to-exclude-the-splash-screen-from-build"></a>Para excluir la pantalla de presentación de la compilación

1. En **Explorador de soluciones**, seleccione la imagen de la pantalla de presentación.

2. En la ventana **propiedades** , establezca la **acción de compilación** en **ninguno**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>Para quitar la pantalla de presentación de una aplicación

En **Explorador de soluciones**, elimine la imagen de la pantalla de presentación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.SplashScreen>
- [Cómo: agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
