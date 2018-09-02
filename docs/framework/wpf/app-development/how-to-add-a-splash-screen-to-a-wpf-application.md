---
title: 'Cómo: Agregar una pantalla de presentación a una aplicación WPF'
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 46efa041736870c5c0f08baa321ef0dc53cacc0d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402931"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Cómo: Agregar una pantalla de presentación a una aplicación WPF

En este tema se muestra cómo agregar una ventana de inicio o *pantalla de presentación*, a una aplicación de Windows Presentation Foundation (WPF).

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>Para agregar una imagen existente como una pantalla de presentación

1.  Crear o encontrar una imagen que desea usar para la pantalla de presentación. Puede usar cualquier formato de imagen que es compatible con Windows Imaging Component (WIC). Por ejemplo, puede usar el formato BMP, GIF, JPEG, PNG o TIFF.

2.  Agregue el archivo de imagen al proyecto de aplicación de WPF.

3.  En **el Explorador de soluciones**, seleccione la imagen.

4.  En la ventana Propiedades, haga clic en la flecha de lista desplegable para la **acción de compilación** propiedad.

5.  Seleccione **SplashScreen** en la lista desplegable.

6.  Presione **F5** para compilar y ejecutar la aplicación.

     La imagen de pantalla de presentación aparece en el centro de la pantalla y luego desaparece cuando aparezca la ventana principal de la aplicación.

## <a name="to-exclude-the-splash-screen-from-build"></a>Para excluir de la pantalla de presentación de compilación

1.  En **el Explorador de soluciones**, seleccione la imagen de pantalla de presentación.

2.  En el **propiedades** ventana, establezca el **acción de compilación** a **ninguno**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>Para quitar la pantalla de presentación de una aplicación

En **el Explorador de soluciones**, elimine la imagen de pantalla de presentación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.SplashScreen>
- [Cómo: agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
