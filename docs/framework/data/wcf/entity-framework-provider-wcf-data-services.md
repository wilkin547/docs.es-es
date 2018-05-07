---
title: Proveedor de Entity Framework (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 0b6e76e6c05a091c57f27fc759044d3567cd976a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="entity-framework-provider-wcf-data-services"></a>Proveedor de Entity Framework (Data Services de WCF)
Al igual que ocurre con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ADO.NET Entity Framework está basado en Entity Data Model, que es un tipo de modelo entidad-relación. Entity Framework traduce las operaciones en su implementación de Entity Data Model, que se denomina la *modelo conceptual*, en operaciones equivalentes sobre un origen de datos. De esta forma, Entity Framework se convierte en un proveedor ideal para los servicios de datos basados en datos relacionales y se puede usar cualquier base de datos con un proveedor de datos que admita Entity Framework con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Para obtener una lista de los orígenes de datos que son compatibles con Entity Framework, vea [proveedores de terceros para Entity Framework](http://go.microsoft.com/fwlink/?LinkId=143699).  
  
 En un modelo conceptual, el contenedor de entidades es la raíz del servicio. Debe definir un modelo conceptual en Entity Framework antes de que un servicio de datos pueda exponer los datos. Para obtener más información, consulte [Cómo: crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite el modelo de simultaneidad optimista al permitirle definir un token de simultaneidad para una entidad. El servicio de datos utiliza este token de simultaneidad, que incluye una o más propiedades de la entidad, para determinar si se ha producido un cambio en los datos que se solicitan, que se están actualizando o eliminando. Cuando los valores de token obtenidos de la eTag de la solicitud difieren de los valores actuales de la entidad, el servicio de datos inicia una excepción. Para indicar que una propiedad forma parte del token de simultaneidad, debe aplicar el atributo `ConcurrencyMode="Fixed"` en el modelo de datos definido por el proveedor de [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. El token de simultaneidad no puede incluir ninguna propiedad clave ni de navegación. Para obtener más información, consulte [actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Para obtener más información acerca de Entity Framework, vea [Introducción a Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Proveedores de Data Services](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Proveedor de reflexión](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
