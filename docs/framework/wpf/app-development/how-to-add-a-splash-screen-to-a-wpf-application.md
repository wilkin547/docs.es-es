---
title: "Cómo: Agregar una pantalla de presentación a una aplicación WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 973f35f6bfa259490a9423bf0b69d676ad968372
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Cómo: Agregar una pantalla de presentación a una aplicación WPF
Este tema muestra cómo agregar una ventana de inicio, o *pantalla de presentación*, a una aplicación de Windows Presentation Foundation (WPF).  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>Para agregar una imagen existente como una pantalla de presentación  
  
1.  Cree o busque una imagen que se va a utilizar para la pantalla de presentación. Puede utilizar cualquier formato de imagen que sea compatible con Windows Imaging Component (WIC). Por ejemplo, puede usar el formato BMP, GIF, JPEG, PNG o TIFF.  
  
2.  Agregue el archivo de imagen al proyecto de aplicación de WPF. Para obtener más información, consulte [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  En el Explorador de soluciones, seleccione la imagen.  
  
4.  En la ventana Propiedades, haga clic en la flecha de lista desplegable para la **acción de compilación** propiedad.  
  
5.  Seleccione **SplashScreen** en la lista desplegable.  
  
    > [!NOTE]
    >  Si no ve el **SplashScreen** opción, asegúrese de comprobar que está usando [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 o posterior.  
  
6.  Presione F5 para compilar y ejecutar la aplicación.  
  
     La imagen de la pantalla de presentación aparece en el centro de la pantalla y, a continuación, desaparece cuando aparezca la ventana de la aplicación principal.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Para quitar la pantalla de presentación de una aplicación  
  
1.  En el Explorador de soluciones, seleccione la imagen de la pantalla de presentación.  
  
2.  En la ventana Propiedades, establezca la **acción de compilación** a **ninguno**.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Para quitar la pantalla de presentación de una aplicación  
  
-   En el Explorador de soluciones, elimine la imagen de la pantalla de presentación.  
  
-   Excluya la imagen de la pantalla de presentación del proyecto.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.SplashScreen>  
 [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
