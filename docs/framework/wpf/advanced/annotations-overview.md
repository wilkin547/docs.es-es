---
title: Información general sobre anotaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 433fee08d44720640d3f9d1bf2511a6a267eb58e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145467"
---
# <a name="annotations-overview"></a>Información general sobre anotaciones
Escribir notas o comentarios en documentos impresos es una actividad tan habitual que prácticamente la subestimamos. Las notas o los comentarios son "anotaciones" que se agregan a un documento para marcar información o resaltar elementos de interés para su posterior referencia. Aunque escribir notas en documentos impresos es fácil y habitual, la capacidad de agregar comentarios personales a documentos electrónicos, si la hay, suele ser muy limitada.  
  
 En este tema se revisan varios tipos comunes de anotaciones, específicamente notas adhesivas y resaltados, e ilustra cómo Microsoft Annotations Framework facilita estos tipos de anotaciones en aplicaciones a través de Windows Presentation Foundation (WPFWPF ) controles de visualización de documentos.  WpfWPF controles de visualización <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentScrollViewer>de documentos que admiten anotaciones incluyen y , así como controles derivados de <xref:System.Windows.Controls.Primitives.DocumentViewerBase> tales como <xref:System.Windows.Controls.DocumentViewer> y <xref:System.Windows.Controls.FlowDocumentPageViewer>.  

<a name="caf1_type_stickynotes"></a>
## <a name="sticky-notes"></a>Notas rápidas  
 Una nota rápida típica contiene la información escrita en un pequeño trozo de papel de color que se "pega" en un documento. Las notas adhesivas digitales proporcionan una funcionalidad similar para los documentos electrónicos, pero con la flexibilidad añadida para incluir muchos otros tipos de contenido, como texto mecanografiado, notas manuscritas (por ejemplo, trazos de "tinta" de Tablet PC) o enlaces web.  
  
 La siguiente ilustración muestra algunos ejemplos de anotaciones de resaltado, notas rápidas de texto y notas rápidas de lápiz.  
  
 ![Anotaciones de resaltar, texto y nota adhesiva manuscrita.](./media/caf-stickynote.jpg "CAF_StickyNote")  
  
 En el ejemplo siguiente se muestra el método que puede usar para habilitar la compatibilidad con las anotaciones de la aplicación.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>
## <a name="highlights"></a>Aspectos destacados  
 Las personas usan métodos creativos para atraer la atención a los elementos de interés cuando marcan un documento impreso, como subrayar, resaltar, rodear palabras de una frase con un círculo o dibujar marcas o notaciones en el margen.  Resaltar anotaciones en Microsoft Annotations Framework proporcionan una característica similar para marcar la información que se muestra en WPFWPF controles de visualización de documentos.  
  
 En la ilustración siguiente se muestra un ejemplo de una anotación de resaltado.  
  
 ![Anotación de resaltar](./media/caf-callouts.png "CAF_Callouts")  
  
 Normalmente, los usuarios crean anotaciones seleccionando primero algún texto o <xref:System.Windows.Controls.ContextMenu> un elemento de interés y, a continuación, haciendo clic con el botón derecho para mostrar una de las opciones de anotación.  En el ejemplo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se muestra <xref:System.Windows.Controls.ContextMenu> el que puede usar para declarar un comando con enrutado al que los usuarios pueden tener acceso para crear y administrar anotaciones.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>
## <a name="data-anchoring"></a>Delimitación de datos  
 El marco de trabajo de anotaciones enlaza anotaciones a los datos que el usuario selecciona, no solo a una posición en la vista de visualización. Por lo tanto, si la vista del documento cambia, por ejemplo cuando el usuario se desplaza por la ventana de presentación o cambia su tamaño, la anotación permanece con la selección de datos a la que está enlazada. Por ejemplo, el siguiente gráfico ilustra una anotación que el usuario realizó en una selección de texto. Cuando el documento observa cambios (desplazamiento, cambio de tamaño, escalado u otros movimientos), la anotación de resaltado se mueve con la selección de datos original.  
  
 ![Delimitación de datos de anotación](./media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>
## <a name="matching-annotations-with-annotated-objects"></a>Coincidencia de anotaciones con objetos anotados  
 Puede hacer coincidir las anotaciones con los objetos anotados correspondientes. Por ejemplo, considere una aplicación de lector de documentos simple que tiene un panel de comentarios. El panel de comentarios podría ser un cuadro de lista que muestra el texto de una lista de anotaciones ancladas a un documento. Si el usuario selecciona un elemento en el cuadro de lista, la aplicación muestra el párrafo del documento al que está anclado el objeto de anotación correspondiente.  
  
 En el ejemplo siguiente se muestra cómo implementar el controlador de eventos de un cuadro de lista como este que sirve de panel de comentarios.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Otro escenario de ejemplo implica aplicaciones que permiten el intercambio de anotaciones y notas adhesivas entre lectores de documentos a través de correo electrónico. Esta característica permite que estas aplicaciones naveguen en el lector hasta la página que contiene la anotación que se está intercambiando.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [Esquema en anotaciones](annotations-schema.md)
- [Información general sobre ContextMenu](../controls/contextmenu-overview.md)
- [Información general sobre comandos](commanding-overview.md)
- [Información general sobre documentos dinámicos](flow-document-overview.md)
- [Cómo: Agregar un comando a un elemento de menú](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
