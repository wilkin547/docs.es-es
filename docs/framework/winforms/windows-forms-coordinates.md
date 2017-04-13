---
title: "Windows Forms Coordinates | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms coordinates"
  - "screen coordinates"
  - "client coordinates"
  - "coordinates, Windows Forms"
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Windows Forms Coordinates
El sistema de coordenadas de un Windows Form está basado en las coordenadas del dispositivo, y la unidad básica de medida cuando se dibuja en Windows Forms es la unidad de dispositivo \(normalmente, el píxel\).  Los puntos en la pantalla se describen mediante pares de coordenadas x e y, con las coordenadas x aumentando hacia la derecha y las coordenadas y aumentando de la parte superior a la inferior.  La ubicación del origen, relativo a la pantalla, varía dependiendo de si está especificando coordenadas de pantalla o de cliente.  
  
## Coordenadas de pantalla  
 Una aplicación de Windows Forms especifica la posición de la ventana en la pantalla en coordenadas de la pantalla.  En el caso de las coordenadas de pantalla, el origen es la esquina superior izquierda de la pantalla.  La posición completa de la pantalla se suele describir mediante una estructura <xref:System.Drawing.Rectangle> que contiene las coordenadas de la pantalla de dos puntos que definen las esquinas superior izquierda e inferior derecha de la ventana.  
  
## Coordenadas de cliente  
 Una aplicación de Windows Forms especifica la posición de los puntos en un formulario o control mediante las coordenadas de cliente.  El origen de las coordenadas de cliente está en la esquina superior izquierda del área de cliente del control o formulario.  Las coordenadas de cliente aseguran que una aplicación puede usar valores de coordenadas coherentes mientras se dibuja en un formulario o control, sin tener en cuenta la posición del formulario o del control en la pantalla.  
  
 Las dimensiones del área de cliente también se describen mediante una estructura <xref:System.Drawing.Rectangle> que contiene las coordenadas de cliente para esa área.  En todos los casos, la coordenada superior izquierda del rectángulo se incluye en el área de cliente, mientras se excluye la coordenada inferior derecha.  Las operaciones gráficas no incluyen los bordes derecho e inferior de un área de cliente.  Por ejemplo, el método <xref:System.Drawing.Graphics.FillRectangle%2A> rellenará el borde derecho e inferior del rectángulo especificado, pero no incluirá estos bordes.  
  
## Asignación de un tipo de coordenada a otro  
 En ocasiones, es posible que necesite asignar las coordenadas de pantalla a las de cliente.  Esta asignación se puede realizar fácilmente mediante los métodos <xref:System.Windows.Forms.Control.PointToClient%2A> y <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibles en la clase <xref:System.Windows.Forms.Control>.  Por ejemplo, la propiedad <xref:System.Windows.Forms.Control.MousePosition%2A> de <xref:System.Windows.Forms.Control> se ofrece en las coordenadas de pantalla, pero quizá desee convertirlas a coordenadas de cliente.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.PointToClient%2A>   
 <xref:System.Windows.Forms.Control.PointToScreen%2A>