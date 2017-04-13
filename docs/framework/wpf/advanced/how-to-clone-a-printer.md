---
title: "C&#243;mo: Clonar una impresora | Microsoft Docs"
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
  - "clonar colas de impresión"
  - "clonar impresoras"
  - "colas de impresión"
  - "colas de impresión, clonar"
  - "impresoras, clonar"
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Clonar una impresora
En la mayoría de las empresas, en algún punto se adquieren varias impresoras del mismo modelo.  Normalmente, todas ellas se instalan configuraciones casi idénticas.  Instalar cada impresora puede exigir mucho tiempo y dar lugar a errores.  El espacio de nombres <xref:System.Printing.IndexedProperties?displayProperty=fullName> y la clase <xref:System.Printing.PrintServer.InstallPrintQueue%2A> que se exponen con [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] permiten instalar al instante cualquier número de colas de impresión adicionales que se clonan a partir de una existente.  
  
## Ejemplo  
 En el ejemplo siguiente, se clona una segunda cola de impresión a partir de otra existente.  La segunda se diferencia de la primera únicamente en su nombre, ubicación, puerto y estado compartido.  Los pasos principales para hacerlo son los siguientes.  
  
1.  Cree un objeto <xref:System.Printing.PrintQueue> para la impresora existente que va a clonar.  
  
2.  Cree un objeto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> a partir de la propiedad <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del objeto <xref:System.Printing.PrintQueue>.  La propiedad <xref:System.Collections.DictionaryEntry.Value%2A> de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>.  Hay dos maneras de establecer el valor de una entrada en este diccionario.  
  
    -   Utilizar los métodos **Remove** y <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> del diccionario para quitar la entrada y, a continuación, volver a agregarla con el valor deseado.  
  
    -   Utilizar el método <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> del diccionario.  
  
     En el ejemplo siguiente se muestran ambas maneras.  
  
3.  Cree un objeto <xref:System.Printing.IndexedProperties.PrintBooleanProperty> y establezca su propiedad <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> en "IsShared" y su propiedad <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> en `true`.  
  
4.  Utilice el objeto <xref:System.Printing.IndexedProperties.PrintBooleanProperty> como valor de la entrada "IsShared" del objeto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
5.  Cree un objeto <xref:System.Printing.IndexedProperties.PrintStringProperty> y establezca su propiedad <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> en "ShareName" y su propiedad <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> en un valor de tipo <xref:System.String> apropiado.  
  
6.  Utilice el objeto <xref:System.Printing.IndexedProperties.PrintStringProperty> como valor de la entrada "ShareName" del objeto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
7.  Cree otro objeto <xref:System.Printing.IndexedProperties.PrintStringProperty> y establezca su propiedad <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> en "Location" y su propiedad <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> en un valor de tipo <xref:System.String> apropiado.  
  
8.  Utilice el segundo objeto <xref:System.Printing.IndexedProperties.PrintStringProperty> como valor de la entrada "Location" del objeto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
9. Cree una matriz de objetos <xref:System.String>.  Cada elemento es el nombre de un puerto del servidor.  
  
10. Utilice <xref:System.Printing.PrintServer.InstallPrintQueue%2A> para instalar la nueva impresora con los nuevos valores.  
  
 A continuación se muestra un ejemplo.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## Vea también  
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)