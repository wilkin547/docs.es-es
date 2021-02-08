---
description: 'Más información acerca de: uso del enlazador de serialización'
title: Uso del enlazador de serialización
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: ee00d8049ae644525f8013801dc7c453b9ad5aeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798178"
---
# <a name="usage-of-serialization-binder"></a>Uso del enlazador de serialización

Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.SerializationBinder> para cambiar la versión de un tipo genérico cuando se serializa.  
  
## <a name="demonstrates"></a>Muestra  

 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Debate  

 Este ejemplo muestra cómo dos entidades que tienen como destino versiones diferentes del .NET Framework pueden comunicarse mediante el formateador binario y el enlazador de serialización.  
  
Este ejemplo se desarrolló con .NET Remoting. Consta de un servidor que tiene como destino .NET Framework 4, que implementa un contrato con tipos genéricos y dos clientes diferentes, uno de destino .NET Framework 2,0 y otro de destino .NET Framework 4.  
  
 El servidor asocia un objeto <xref:System.Runtime.Serialization.SerializationBinder> al formateador binario para poder cambiar la versión de los tipos de acuerdo con la serialización, de modo que ambos clientes puedan deserializar esos tipos correctamente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1. Para ejecutar el cliente, haga clic con el botón derecho en la solución, SBGenericsVTS (6 proyectos) y, a continuación, seleccione **propiedades**.  
  
2. En **propiedades comunes**, seleccione **proyecto de inicio** y, a continuación, seleccione **proyectos de inicio múltiples**.  
  
3. Seleccione **servidor** primero, **Client20** y, a continuación, **Client40**. Seleccione la acción de **Inicio** en estos tres proyectos y deje el resto establecido en **ninguno**.  
  
4. Haga clic en **Aceptar** y, a continuación, presione F5 para ejecutar el ejemplo.
