---
title: "Creaci&#243;n de una fuente b&#225;sica de Atom | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Creaci&#243;n de una fuente b&#225;sica de Atom
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite crear un servicio que exponga una fuente de distribución.En este tema se discute cómo crear un servicio de distribución que exponga una fuente de distribución Atom.  
  
### Creación de un servicio de distribución básico  
  
1.  Defina un contrato de servicios utilizando una interfaz marcada con el atributo <xref:System.ServiceModel.Web.WebGetAttribute>.Cada operación que se expone como una fuente de distribución debería devolver un objeto <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>.  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Todas las operaciones de servicio que apliquen el <xref:System.ServiceModel.Web.WebGetAttribute> se asignan a solicitudes HTTP GET.Para asignar su operación a un método HTTP diferente, utilice en su lugar <xref:System.ServiceModel.Web.WebInvokeAttribute>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Crear un servicio básico web HTTP de WCF](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).  
  
2.  Implemente el contrato de servicios.  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3.  Cree un objeto <xref:System.ServiceModel.Syndication.SyndicationFeed> y agregue un autor, categoría y descripción.  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4.  Cree varios objetos <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5.  Agregue los objetos <xref:System.ServiceModel.Syndication.SyndicationItem> a la fuente.  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6.  Devuelva la fuente.  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### Para hospedar el servicio.  
  
1.  Cree un objeto <xref:System.ServiceModel.Web.WebServiceHost>.  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2.  Abra el host del servicio, cargue la fuente desde el servicio, muestre la fuente y espere a que el usuario presione Entrar.  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### Realización de llamadas a GetBlog\(\) mediante HTTP GET  
  
1.  Abra Internet Explorer, escriba la siguiente URL y presione Entrar: http:\/\/localhost:8000\/BlogService\/GetBlog  
  
     La URL contiene la dirección base del servicio \(http:\/\/localhost:8000\/BlogService\), la dirección relativa del extremo y la operación del servicio que se va a llamar.  
  
### Llamar a GetBlog\(\) mediante código  
  
1.  Cree un <xref:System.Xml.XmlReader> con la dirección base y el método al que está llamando.  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2.  Llame al método estático <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, pasando el <xref:System.Xml.XmlReader> que acaba de crear.  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     Esto invoca la operación de servicio y rellena una nueva <xref:System.ServiceModel.Syndication.SyndicationFeed> con el formateador devuelto desde la operación del servicio.  
  
3.  Obtenga acceso al objeto de fuente.  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## Ejemplo  
 A continuación, se muestra una lista de código completa en este ejemplo.  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## Compilar el código  
 Al compilar el código anterior, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.  
  
## Vea también  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Web.WebGetAttribute>