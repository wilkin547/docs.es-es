---
title: 'Cómo: Clonar una impresora'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: 8f3a9c3b4d9f4bcbe3a6ffcff9868aa7b19b8f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-clone-a-printer"></a>Cómo: Clonar una impresora
En algún momento, la mayoría de las empresas comprará varias impresoras del mismo modelo. Normalmente, todas ellas se instalan con valores de configuración prácticamente idénticos. Instalar cada impresora puede llevar mucho tiempo y es proclive a errores. El <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> espacio de nombres y el <xref:System.Printing.PrintServer.InstallPrintQueue%2A> clase que se exponen a través de Microsoft .NET Framework permite instalar al instante cualquier número de colas de impresión adicionales que se clonan desde una cola de impresión existente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se clona una segunda cola de impresión de una cola de impresión existente. El segundo es distinto del primero solo en su nombre, la ubicación, el puerto y el estado compartido. Los pasos principales para esto son los siguientes.  
  
1.  Crear un <xref:System.Printing.PrintQueue> objeto para la impresora existente que se va a clonar.  
  
2.  Crear un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> desde el <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> de la <xref:System.Printing.PrintQueue>. El <xref:System.Collections.DictionaryEntry.Value%2A> propiedad de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>. Hay dos maneras de establecer el valor de una entrada en este diccionario.  
  
    -   Usar el diccionario **quitar** y <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> métodos para quitar la entrada y, a continuación, vuelva a agregarlo con el valor deseado.  
  
    -   Usar el diccionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> método.  
  
     En el ejemplo siguiente se muestra ambas maneras.  
  
3.  Crear un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> en "IsShared" y su <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.  
  
4.  Use la <xref:System.Printing.IndexedProperties.PrintBooleanProperty> objeto que se va a ser el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada "IsShared".  
  
5.  Crear un <xref:System.Printing.IndexedProperties.PrintStringProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "ShareName" y su <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> a un correspondiente <xref:System.String>.  
  
6.  Use la <xref:System.Printing.IndexedProperties.PrintStringProperty> objeto que se va a ser el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada "ShareName".  
  
7.  Crear otra <xref:System.Printing.IndexedProperties.PrintStringProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "Location" y su <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> a un correspondiente <xref:System.String>.  
  
8.  Use la segunda <xref:System.Printing.IndexedProperties.PrintStringProperty> objeto que se va a ser el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada "Location".  
  
9. Crear una matriz de <xref:System.String>s. Cada elemento es el nombre de un puerto en el servidor.  
  
10. Utilice <xref:System.Printing.PrintServer.InstallPrintQueue%2A> para instalar la nueva impresora con los nuevos valores.  
  
 Un ejemplo es menor que.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)
