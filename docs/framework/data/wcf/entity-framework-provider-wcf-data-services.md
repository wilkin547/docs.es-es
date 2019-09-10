---
title: Proveedor de Entity Framework (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 5a40eeafafef56902a9ae5037e6bc946b598f752
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854084"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Proveedor de Entity Framework (Data Services de WCF)
Al igual que ocurre con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ADO.NET Entity Framework está basado en Entity Data Model, que es un tipo de modelo entidad-relación. El Entity Framework traduce las operaciones en su implementación de la Entity Data Model, que se denomina *modelo conceptual*, en operaciones equivalentes en un origen de datos. De esta forma, Entity Framework se convierte en un proveedor ideal para los servicios de datos basados en datos relacionales y se puede usar cualquier base de datos con un proveedor de datos que admita Entity Framework con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Para obtener una lista de los orígenes de datos que admiten actualmente el Entity Framework, consulte [proveedores de terceros para la Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 En un modelo conceptual, el contenedor de entidades es la raíz del servicio. Debe definir un modelo conceptual en Entity Framework antes de que un servicio de datos pueda exponer los datos. Para obtener más información, consulte [Cómo Cree un servicio de datos mediante un origen](create-a-data-service-using-an-adonet-ef-data-wcf.md)de datos de ADO.NET Entity Framework.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]admite el modelo de simultaneidad optimista al permitirle definir un token de simultaneidad para una entidad. El servicio de datos utiliza este token de simultaneidad, que incluye una o más propiedades de la entidad, para determinar si se ha producido un cambio en los datos que se solicitan, que se están actualizando o eliminando. Cuando los valores de token obtenidos de la eTag de la solicitud difieren de los valores actuales de la entidad, el servicio de datos inicia una excepción. Para indicar que una propiedad forma parte del token de simultaneidad, debe aplicar el atributo `ConcurrencyMode="Fixed"` en el modelo de datos definido por el proveedor de Entity Framework. El token de simultaneidad no puede incluir ninguna propiedad clave ni de navegación. Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).  
  
 Para obtener más información sobre el Entity Framework, consulte [información general sobre Entity Framework](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>Vea también

- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
- [Proveedor de reflexión](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
