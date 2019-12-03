---
title: Agilidad criptográfica en la seguridad de WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714923"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilidad criptográfica en la seguridad de WCF

En este ejemplo se muestra cómo especificar en un algoritmo estándar o personalizado para proporcionar una implementación criptográfica de Agile en un servicio y cliente de Windows Communication Foundation (WCF). El ejemplo consta de los proyectos siguientes:

**Servicio**

Se trata de un servicio WCF autohospedado que implementa la interfaz de `ICalculator` y protege el punto de conexión mediante el <xref:System.ServiceModel.WSHttpBinding> con la sesión segura y la sesión confiable deshabilitada. El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.

**Cliente**

Se trata de un cliente WCF que tiene acceso al servicio después de la autenticación correcta. Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio. El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.

## <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Abra la solución CryptoAgility. sln en Visual Studio 2012.

2. Presione Ctrl+MAYÚS+B para compilar la solución.

3. Abra el explorador de archivos y vaya al directorio \WCF\Basic\Security\CryptoAgility\Service\bin y ejecute el archivo Service. exe con privilegios de administrador haciendo clic con el botón secundario en Service. exe y seleccionando **Ejecutar como administrador**.

4. Navegue hasta el directorio \WCF\Basic\Security\CryptoAgility\Client\bin y ejecute el archivo client.exe normalmente.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>Vea también

- [Seguridad de Windows Communication Foundation](../feature-details/security.md)
