---
title: Procedimiento Personalizar comportamientos de enlace de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: c878096cba7d31e0b48727213ee1bb8239b8f690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790753"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Procedimiento Personalizar comportamientos de enlace de datos (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede proporcionar lógica personalizada a la que <xref:System.Data.Services.Client.DataServiceCollection%601> llama cuando se agrega o se quita un objeto de la colección de enlaces o cuando se detecta un cambio en una propiedad. Esta lógica personalizada se proporciona como métodos, a los que <xref:System.Func%602> se hace referencia como delegados `false` , que devuelven un valor de cuando se debe seguir realizando el comportamiento `true` predeterminado cuando se completa el método personalizado y cuando el procesamiento posterior del el evento debe detenerse.  
  
 Los ejemplos de este tema proporcionan métodos personalizados para los parámetros `entityChanged` y `entityCollectionChanged` de la clase <xref:System.Data.Services.Client.DataServiceCollection%601>. En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente página de codigos subyacente para el archivo XAML crea una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> con métodos personalizados a los que se llama cuando se producen cambios en los datos enlazados a la colección de enlaces. Cuando se produce el evento <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>, el método proporcionado evita que se elimine del servicio de datos un elemento que se ha quitado de la colección de enlaces. Cuando se produce el evento <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>, se valida el valor de `ShipDate` para asegurarse de que no se realizan cambios en los pedidos que ya han enviado.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente define la ventana del ejemplo anterior.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
