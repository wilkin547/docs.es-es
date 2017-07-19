---
title: "C&#243;mo: Mostrar un control en el cuadro de di&#225;logo Elegir elementos de cuadro de herramientas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "caché global de ensamblados, cuadro de diálogo Elegir elementos del cuadro de herramientas"
  - "AssemblyFoldersEx, cuadro de diálogo Elegir elementos del cuadro de herramientas"
  - "controles, mostrar en el cuadro de diálogo Elegir elementos del cuadro de herramientas"
  - "registro de la carpeta de ensamblados, cuadro de diálogo Elegir elementos del cuadro de herramientas"
  - "Cuadro de diálogo Elegir elementos del cuadro de herramientas, mostrar control"
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Mostrar un control en el cuadro de di&#225;logo Elegir elementos de cuadro de herramientas
Conforme desarrolle y distribuya controles, es posible que desee que esos controles aparezcan en el cuadro de diálogo **Elegir elementos del cuadro de herramientas**, que se muestra al hacer clic con el botón secundario en **Cuadro de herramientas** y seleccionar **Elegir elementos**.  Puede hacer que un control aparezca en este cuadro de diálogo mediante el procedimiento de registro AssemblyFoldersEx.  
  
### Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas  
  
-   Instale el ensamblado del control en la memoria caché global de ensamblados.  Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
     O bien  
  
-   Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro de AssemblyFoldersEx.  AssemblyFoldersEx es una ubicación del Registro donde los proveedores de terceros almacenan las rutas de acceso para cada versión de .NET Framework que admiten.  La resolución en tiempo de diseño puede buscar en esta ubicación del Registro para encontrar los ensamblados de referencia.  En el script de Registro se pueden especificar los controles que desea que aparezcan en el cuadro de herramientas.  Para obtener más información, vea [Implementar un control personalizado y ensamblados en tiempo de diseño](http://msdn.microsoft.com/es-es/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## Vea también  
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/es-es/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [Implementar un control personalizado y ensamblados en tiempo de diseño](http://msdn.microsoft.com/es-es/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)   
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)   
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)