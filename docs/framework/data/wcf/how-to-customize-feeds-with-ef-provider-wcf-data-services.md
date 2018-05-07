---
title: 'Cómo: Personalizar fuentes con el proveedor de Entity Framework (Data Services de WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: bd29f6154297c2410294af14952d3d79201966ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Cómo: Personalizar fuentes con el proveedor de Entity Framework (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a los elementos no usados que se definen en el protocolo AtomPub. En este tema se explica cómo definir los atributos de asignación para los tipos de entidad en un modelo de datos definido en un archivo .edmx utilizando el proveedor de Entity Framework. Para obtener más información, consulte [personalización de fuente](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 En este tema modificará manualmente el archivo .edmx generado por la herramienta que contiene el modelo de datos. Dado que Entity Designer no admite las extensiones al modelo de datos, debe modificar manualmente el archivo. Para obtener más información acerca del archivo .edmx que generan las herramientas de Entity Data Model, vea [información general sobre archivo .edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4). En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>Para modificar manualmente el archivo Northwind.edmx para agregar los atributos de personalización de fuente  
  
1.  En **el Explorador de soluciones**, haga clic en el `Northwind.edmx` de archivos y, a continuación, haga clic en **abrir con**.  
  
2.  En el **abrir con - Northwind.edmx** cuadro de diálogo, seleccione **Editor XML**y, a continuación, haga clic en **Aceptar**.  
  
3.  Busque el elemento `ConceptualModels` y reemplace el tipo de entidad `Customers` existente con el siguiente elemento que contiene los atributos de asignación de personalización de la fuente:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4.  Guarde los cambios y cierre el archivo Northwind.edmx.  
  
5.  (Opcional) Haga clic en el archivo Northwind.edmx y, a continuación, haga clic en **ejecutar herramienta personalizada**.  
  
     Esto regenera el archivo de capa de objeto, que puede ser necesario.  
  
6.  Compile de nuevo el proyecto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo anterior se devuelve el resultado siguiente para el identificador URI `http://myservice/``Northwind.svc/Customers('ALFKI')`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>Vea también  
 [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)
