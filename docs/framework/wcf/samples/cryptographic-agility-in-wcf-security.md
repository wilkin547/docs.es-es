---
description: 'Más información sobre: agilidad criptográfica en la seguridad de WCF'
title: Agilidad criptográfica en la seguridad de WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: ab46034b16a846f7399220480fc928655d931be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778352"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilidad criptográfica en la seguridad de WCF

En este ejemplo se muestra cómo especificar en un algoritmo estándar o personalizado para proporcionar una implementación criptográfica de Agile en un servicio y cliente de Windows Communication Foundation (WCF). El ejemplo consta de los proyectos siguientes:

**Servicio**

Se trata de un servicio WCF autohospedado que implementa la `ICalculator` interfaz y protege el punto de conexión mediante <xref:System.ServiceModel.WSHttpBinding> con la sesión segura y la sesión confiable deshabilitada. El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.

**Cliente**

Se trata de un cliente WCF que tiene acceso al servicio después de la autenticación correcta. Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio. El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.

## <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Abra la solución CryptoAgility. sln en Visual Studio 2012.

2. Presione CTRL+MAYÚS+B para compilar la solución.

3. Abra el explorador de archivos y vaya al directorio \WCF\Basic\Security\CryptoAgility\Service\bin y ejecute el archivo service.exe con privilegios de administrador haciendo clic con el botón secundario en service.exe y seleccionando **Ejecutar como administrador**.

4. Navegue hasta el directorio \WCF\Basic\Security\CryptoAgility\Client\bin y ejecute el archivo client.exe normalmente.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>Vea también

- [Seguridad en Windows Communication Foundation](../feature-details/security.md)
