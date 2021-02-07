---
description: 'Más información sobre: criterios de búsqueda personalizados'
title: Criterios de búsqueda personalizados
ms.date: 03/30/2017
ms.assetid: b2723929-8829-424d-8015-a37ba2ab4f68
ms.openlocfilehash: 71082f303e3464e27e1bad3995d20b5f6cf7d647
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732571"
---
# <a name="custom-find-criteria"></a>Criterios de búsqueda personalizados

Este ejemplo muestra cómo crear una concordancia de ámbito personalizada usando la lógica y cómo implementar un servicio de detección personalizado. Los clientes utilizan la funcionalidad de concordancia de ámbito personalizada para refinar y seguir usando la funcionalidad de búsqueda proporcionada por la detección WCF. El escenario que abarca este ejemplo es el siguiente:  
  
1. Un cliente busca un servicio de calculadora.  
  
2. Para refinar su búsqueda, el cliente debe utilizar una regla de concordancia de ámbito personalizada.  
  
3. Según esta regla, un servicio responde al cliente si su extremo coincide con cualquiera de los ámbitos especificados por el cliente.  
  
## <a name="demonstrates"></a>Muestra  
  
- Crear un servicio de descarga personalizado.  
  
- Implementar una coincidencia del ámbito personalizada por algoritmo.  
  
## <a name="discussion"></a>Debate  

 El cliente está buscando criterios de coincidencia de tipo "OR". Un servicio responde si los ámbitos de sus puntos de conexión coinciden con alguno de los ámbitos que proporciona el cliente. En este caso, el cliente busca un servicio de calculadora que tenga cualquiera de los ámbitos de la siguiente lista:  
  
1. `net.tcp://Microsoft.Samples.Discovery/RedmondLocation`  
  
2. `net.tcp://Microsoft.Samples.Discovery/SeattleLocation`  
  
3. `net.tcp://Microsoft.Samples.Discovery/PortlandLocation`  
  
 Para lograr esto, el cliente dirige los servicios para utilizar una regla de concordancia de ámbito personalizada pasando una coincidencia de ámbito personalizada a través de URI. Para facilitar la coincidencia de ámbito personalizada, el servicio debe utilizar un servicio de descarga personalizado que entiende la regla de coincidencia de ámbito personalizada e implemente la lógica de coincidencia asociada.  
  
 En el proyecto de cliente, abra el archivo Program.cs. Observe que el campo `ScopeMatchBy` del objeto `FindCriteria` está establecido en un URI concreto. Este identificador se envía al servicio. Si el servicio no entiende esta regla, omite la solicitud de la búsqueda del cliente.  
  
 Abra el proyecto de servicio. Se utilizan tres archivos para implementar el Servicio de descarga personalizado:  
  
1. **AsyncResult.CS**: se trata de la implementación de `AsyncResult` que requieren los métodos de detección.  
  
2. **CustomDiscoveryService.CS**: este archivo implementa el servicio de detección personalizado. La implementación extiende la clase <xref:System.ServiceModel.Discovery.DiscoveryService> e invalida los métodos necesarios. Observe la implementación del método <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>. El método comprueba si el cliente especificó la coincidencia de ámbito personalizada por regla. Se trata del mismo URI personalizado que el cliente especificó previamente. Si se especifica la regla personalizada, se sigue la ruta de acceso del código que implementa la lógica de coincidencia "OR".  
  
     Esta lógica personalizada pasa por todos los ámbitos de cada uno de los puntos de conexión que el servicio tiene. Si alguno de los ámbitos del punto de conexión coincide con alguno de los ámbitos proporcionados por el cliente, el servicio de descarga agrega ese punto de conexión a la respuesta que se devuelve al cliente.  
  
3. **CustomDiscoveryExtension.CS**: el último paso para implementar el servicio de detección es conectar esta implementación del servicio de detección personalizado al host de servicio. La clase del asistente que se utiliza aquí es la clase `CustomDiscoveryExtension`. Esta clase extiende la clase <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension>. El usuario debe invalidar el método <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A>. En este caso, el método devuelve una instancia del servicio de detección personalizado que se creó antes. `PublishedEndpoints` es <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> que contiene todos los extremos de aplicación que se agregan a <xref:System.ServiceModel.ServiceHost>. El servicio de detección personalizado lo utiliza para rellenar su lista interna. El usuario puede agregar también otros metadatos de punto de conexión.  
  
 Por último, abra Program.cs. Observe que tanto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> como `CustomDiscoveryExtension` se agregan al host. Una vez hecho esto, si el host tiene un punto de conexión sobre el que recibir los mensajes de detección, la aplicación puede utilizar el servicio de detección personalizado.  
  
 Observe que el cliente puede encontrar el servicio sin conocer su dirección.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Abra la solución que contiene el proyecto.  
  
2. Compile el proyecto.  
  
3. Ejecute la aplicación de servicio.  
  
4. Ejecute la aplicación cliente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\CustomFindCriteria`
