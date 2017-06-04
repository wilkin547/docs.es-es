---
title: "C&#243;mo: Quitar un ensamblado de la memoria cach&#233; global de ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], caché global de ensamblados"
  - "eliminar ensamblados de la memoria caché global de ensamblados"
  - "GAC (caché global de ensamblados), quitar ensamblados"
  - "Gacutil.exe"
  - "Caché global de ensamblados (herramienta)"
  - "caché global de ensamblados, quitar ensamblados"
  - "quitar ensamblados de caché global de ensamblados"
  - "ensamblados con nombre seguro, caché global de ensamblados"
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Quitar un ensamblado de la memoria cach&#233; global de ensamblados
Hay dos formas de quitar un ensamblado de la caché global de ensamblados \(GAC\):  
  
-   Con la [herramienta Caché global de ensamblados \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  Puede usar esta opción para desinstalar los ensamblados que haya colocado en la GAC durante el desarrollo y las pruebas.  
  
-   Con [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).  Debe usar esta opción para desinstalar ensamblados al probar los paquetes de instalación y en sistemas de producción.  
  
### Quitar un ensamblado con Gacutil.exe  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     **gacutil –u** \<*nombre del ensamblado*\>  
  
     En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a quitar de la caché global de ensamblados.  
  
    > [!WARNING]
    >  No debe utilizar Gacutil.exe para quitar ensamblados en sistemas de producción porque existe la posibilidad de que alguna aplicación necesite aún el ensamblado.  En su lugar, debe usar el instalador de Windows, que mantiene un recuento de referencias para cada ensamblado que se instala en la GAC.  
  
 En el ejemplo siguiente se quita un ensamblado llamado `hello.dll` de la caché global de ensamblados.  
  
```  
gacutil -u hello  
```  
  
### Quitar un ensamblado con Windows Installer  
  
1.  En la aplicación **Programas y características** del **Panel de Control**, seleccione la aplicación que quiere desinstalar.  Si el paquete de instalación colocó ensamblados en la GAC, Windows Installer los quitará si otra aplicación no lo está usando.  
  
    > [!NOTE]
    >  Windows Installer mantiene un recuento de referencias para los ensamblados instalados en la GAC.  Un ensamblado se quita de la GAC solo cuando su recuento de referencias llega a cero, lo que indica que no lo está usando ninguna aplicación instalada por un paquete de Windows Installer.  
  
## Vea también  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)