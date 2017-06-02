---
title: "GetCustomUI | Microsoft Docs"
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
  - "mensajes de error personalizados [WPF]"
  - "GetCustomUI (método)"
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# GetCustomUI
PresentationHost.exe llama a esta función para obtener mensajes personalizados de progreso y de error del host, si se implementa.  
  
## Sintaxis  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### Parámetros  
 `pwzProgressAssemblyName`  
  
 \[out\] Puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.  
  
 `pwzProgressClassName`  
  
 \[out\] Nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferentemente un archivo [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] en que <xref:System.Windows.Controls.Page> es el elemento de nivel superior.  Esta clase reside en el ensamblado que se especifica mediante `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 \[out\] Puntero al ensamblado que contiene la interfaz de usuario de error proporcionada por el host.  
  
 `pwzErrorClassName`  
  
 \[out\] Nombre de la clase que es la interfaz de usuario de error proporcionada por el host, preferentemente un archivo XAML en que <xref:System.Windows.Controls.Page> es el elemento de nivel superior.  Esta clase reside en el ensamblado que se especifica mediante `pwzErrorAssemblyName`.  
  
## Valor de propiedad y valor devuelto  
 HRESULT: Se omite.  
  
## Comentarios  
 Una aplicación host puede tener un tema concreto que las interfaces de usuario predeterminadas de PresentationHost.exe no puedan respetar.  En este caso, la aplicación host puede implementar [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) para devolver interfaces de usuario de progreso y error a PresentationHost.exe.  PresentationHost.exe siempre llamará a [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) antes de utilizar sus interfaces de usuario predeterminadas.  
  
 Se llama a esta función una vez durante la inicialización de PresentationHost.  
  
## Vea también  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)