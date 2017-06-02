---
title: "C&#243;mo: Agregar una pantalla de presentaci&#243;n a una aplicaci&#243;n WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "pantalla de presentación [WPF]"
  - "SplashScreen (clase) [WPF]"
  - "ventana de inicio [WPF]"
  - "WPF, pantalla de presentación"
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Agregar una pantalla de presentaci&#243;n a una aplicaci&#243;n WPF
En este tema se muestra cómo agregar una ventana de inicio o *pantalla de presentación*, a una aplicación de Windows Presentation Foundation \(WPF\).  
  
### Para agregar una imagen existente como una pantalla de presentación  
  
1.  Cree o busque la imagen que desea utilizar para la pantalla de presentación.  Puede utilizar cualquier formato de imagen compatible con Windows Imaging Component \(WIC\).  Por ejemplo, se puede utilizar el formato BMP, GIF, JPEG, PNG o TIFF.  
  
2.  Agregue el archivo de imagen al proyecto de aplicación de WPF.  Para obtener más información, vea [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/es-es/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  En el Explorador de soluciones, seleccione la imagen.  
  
4.  En la ventana Propiedades, haga clic en la flecha de la lista desplegable de la propiedad **Acción de compilación**.  
  
5.  Seleccione **SplashScreen** en la lista desplegable.  
  
    > [!NOTE]
    >  Si no ve la opción **SplashScreen**, asegúrese de estar utilizando [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 o posterior.  
  
6.  Presione F5 para compilar y ejecutar la aplicación.  
  
     La imagen de la pantalla de presentación aparece en el centro de la pantalla y, a continuación, se desvanece cuando aparece la ventana de la aplicación principal.  
  
### Para quitar la pantalla de presentación de una aplicación  
  
1.  En el Explorador de soluciones, seleccione la imagen de la pantalla de presentación.  
  
2.  En la ventana Propiedades, establezca **Acción de compilación** en **Ninguna**.  
  
### Para quitar la pantalla de presentación de una aplicación  
  
-   En el Explorador de soluciones, elimine la imagen de la pantalla de presentación.  
  
-   Excluya la imagen de la pantalla de presentación del proyecto.  
  
## Vea también  
 <xref:System.Windows.SplashScreen>   
 [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/es-es/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)