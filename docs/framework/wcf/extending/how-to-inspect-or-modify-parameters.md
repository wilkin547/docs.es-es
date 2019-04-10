---
title: Filtrar para inspeccionar o modificar parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: 2e294b7970a58fad9385802470a514e5a9240495
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303978"
---
# <a name="how-to-inspect-or-modify-parameters"></a>Filtrar para inspeccionar o modificar parámetros
Puede inspeccionar o modificar los mensajes entrantes o salientes para una única operación en un objeto de cliente de Windows Communication Foundation (WCF) o un servicio WCF mediante la implementación de la <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interfaz e insertarlos en el tiempo de ejecución de cliente o servicio. Normalmente se utiliza un comportamiento de operación para agregar inspectores de parámetro en una sola operación; se pueden utilizar otros comportamientos para proporcionar acceso fácil al tiempo de ejecución en un ámbito mayor. Para obtener más información, consulte [los clientes extender](../../../../docs/framework/wcf/extending/extending-clients.md) y [extender distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Inspeccionando o modificando parámetros  
  
1. Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2. Implemente <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (dependiendo del ámbito requerido) para agregar su inspector de parámetro a <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> o las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.  
  
3. Inserte su comportamiento antes de llamar <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o el método <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obtener más información, consulte [configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran, en orden:  
  
-   Una implementación de inspector de parámetro.  
  
-   La implementación de comportamiento que inserta el inspector de parámetro utilizando <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> y <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.  
  
-   Un archivo de configuración que carga y ejecuta el comportamiento del punto de conexión en una aplicación cliente para insertar el inspector de parámetro en el cliente.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Vea también

- [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
