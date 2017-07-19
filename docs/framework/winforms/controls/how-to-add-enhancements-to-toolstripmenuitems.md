---
title: "C&#243;mo: Agregar mejoras a ToolStripMenuItems | Microsoft Docs"
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
  - "marcas de verificación, agregar a menús"
  - "comandos [Windows Forms], agrupar en menús"
  - "imágenes [Windows Forms], agregar a menús"
  - "métodos abreviados de teclado, mostrar en menús"
  - "elementos de menú, agregar marcas de verificación"
  - "elementos de menú, agregar imágenes"
  - "elementos de menú, mostrar teclas de acceso"
  - "elementos de menú, mostrar teclas de método abreviado"
  - "elementos de menú, mostrar separadores"
  - "menús, agrupar comandos"
  - "separadores, mostrar en menús"
  - "ToolStripMenuItems"
  - "ToolStripMenuItems, agregar marcas de verificación"
  - "ToolStripMenuItems, agregar imágenes"
  - "ToolStripMenuItems, mostrar teclas de acceso"
  - "ToolStripMenuItems, mostrar teclas de método abreviado"
  - "ToolStripMenuItems, mostrar barras separadoras"
  - "ToolStripSeparators, mostrar en MenuStrips"
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agregar mejoras a ToolStripMenuItems
Se puede mejorar el uso de los controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> de las maneras siguientes:  
  
-   Agregue marcas de verificación para designar si una característica está activada o no, como si se muestra una regla junto al margen de una aplicación de procesamiento de textos, o para indicar qué archivo de la lista se está mostrando, por ejemplo, en un menú **Ventana**.  
  
-   Agregue imágenes que representan visualmente los comandos de menú.  
  
-   Muestre las teclas de método abreviado para proporcionar un teclado alternativo al mouse para realizar los comandos.  Por ejemplo, al presionar CTRL\+C se realiza el comando **Copy**.  
  
-   Muestre las teclas de acceso para proporcionar un teclado como alternativa al mouse para navegar por el menú.  Al presionar ALT\+F, por ejemplo, se elige el menú **Archivo**.  
  
-   Muestre las barras separadoras para agrupar los comandos relacionados y hacer que los menús sean más legibles.  
  
### Para mostrar una marca de verificación en un comando de menú  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> en `true`.  
  
     Esto también establece la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> en `true`.  Utilice únicamente este procedimiento si desea que el comando de menú aparezca como seleccionado de manera predeterminada, sin tener en cuenta si está seleccionado o no.  
  
### Para mostrar una marca de verificación que cambia el estado con cada clic  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> del control en `true`.  
  
### Para agregar una imagen a un comando de menú  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A> del comando de menú en el nombre de la imagen.  Si la propiedad <xref:System.Windows.Forms.ToolStripItemDisplayStyle> de este comando de menú se establece en <xref:System.Windows.Forms.ToolStripItemDisplayStyle> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, no se puede mostrar la imagen.  
  
> [!NOTE]
>  El margen de la imagen también puede mostrar una marca de verificación si la elige.  Además, puede establecer la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> de la imagen en `true`, y la imagen aparecerá con un borde tramado alrededor en tiempo de ejecución.  
  
### Para mostrar una tecla de método abreviado para un comando de menú  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando de menú en la combinación de teclado deseada, como CTRL\+O para el comando de menú **Abrir**, y establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> en `true`.  
  
### Para mostrar una tecla de método abreviado personalizada para un comando de menú  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> del comando de menú en la combinación de teclas deseada, como CTRL\+SHIFT\+O en lugar de SHIFT\+CTRL\+O y establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> en `true`.  
  
### Para mostrar una tecla de acceso para un comando de menú  
  
-   Cuando establece la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> para el comando de menú, escriba una Y comercial \(&\) antes de la letra que quiere que esté subrayada como tecla de acceso.  Por ejemplo, si escribe  `&Open`  como propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> de un elemento de menú, obtendrá un elemento de menú que aparecerá como **O**pen.  
  
     Para navegar hasta este elemento de menú, presione ALT para asignar el foco a <xref:System.Windows.Forms.MenuStrip> y presione la tecla de acceso del nombre del menú.  Cuando se abra el menú y muestre elementos con teclas de acceso, sólo necesitará presionar la tecla de acceso para seleccionar el comando de menú.  
  
> [!NOTE]
>  No defina teclas de acceso duplicadas, como definir dos veces ALT\+F en el mismo sistema de menú.  No se puede garantizar el orden de selección de las teclas de acceso duplicadas.  
  
### Para mostrar una barra separadora entre los comandos de menú  
  
-   Después de definir el <xref:System.Windows.Forms.MenuStrip> y los elementos que contiene, utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> para agregar los comandos de menú y los controles <xref:System.Windows.Forms.ToolStripSeparator> al <xref:System.Windows.Forms.MenuStrip> en el orden que desea.  
  
     \[Visual Basic\]  
  
    ```  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
  
    ```  
  
     \[C\#\]  
  
    ```  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)