---
title: Procedimiento Habilitar el acceso al servicio de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 260d127107d1ccf1263f4efddd59da9e34306436
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645651"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Procedimiento Habilitar el acceso al servicio de datos (WCF Data Services)
En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], debe permitir explícitamente el acceso a los recursos expuestos por un servicio de datos. Esto significa que después de crear un nuevo servicio de datos, debe proporcionar explícitamente acceso a los recursos individuales como conjuntos de entidades. En este tema se muestra cómo habilitar la lectura y acceso de escritura a cinco de la entidad se establece en el servicio de datos de Northwind que se crea cuando se completa la [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Dado que la enumeración <xref:System.Data.Services.EntitySetRights> se define utilizando <xref:System.FlagsAttribute>, puede utilizar un operador OR lógico para especificar varios permisos para un único conjunto de entidades.  
  
> [!NOTE]
>  Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos. En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos, también debería proteger la aplicación. Para obtener más información, consulte [proteger los sitios Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).  
  
### <a name="to-enable-access-to-the-data-service"></a>Para habilitar el acceso al servicio de datos  
  
- En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     De esta forma, los clientes pueden tener acceso de lectura y escritura a los conjuntos de entidades de `Orders` y `Order_Details`, y acceso de solo lectura a los conjuntos de entidades de `Customers`.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Desarrollar un servicio de datos WCF que se ejecutan en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)
- [Configuración del servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
