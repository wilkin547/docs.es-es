---
description: Más información acerca de cómo configurar el servicio COM+.
title: Procedimiento para configurar los parámetros de los servicios COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: 95d58c9db5fa4d3c5e1830401b1ab0651a56d265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734950"
---
# <a name="how-to-configure-com-service-settings"></a>Procedimiento para configurar los parámetros de los servicios COM+

Cuando se agrega o quita una interfaz de aplicaciones mediante la herramienta de configuración de servicio de COM+, la configuración del servicio web se actualiza en el archivo de configuración de la aplicación. En el modo hospedado de COM+, el archivo de Application.config se coloca en el directorio raíz de la aplicación (%ProgramFiles%\ComPlus Applications Applications \\ {AppID} es el valor predeterminado). En cualquiera de los modos hospedados en la web, el archivo Web.config se encuentra en el directorio vroot especificado.  
  
> [!NOTE]
> La utilización de la firma de los mensajes protege de la alteración de los mensajes entre el cliente y un servidor. Además, la utilización del cifrado en el nivel del mensaje o del transporte protege contra la divulgación de información de los mensajes entre un cliente y un servidor. Al igual que con los servicios de Windows Communication Foundation (WCF), debe usar la limitación para limitar el número de llamadas simultáneas, conexiones, instancias y operaciones pendientes. Así se contribuye a evitar el consumo excesivo de recursos. El comportamiento del límite de peticiones se especifica mediante los valores del archivo de configuración del servicio.  
  
## <a name="example"></a>Ejemplo  

 Considere un componente que implementa la siguiente interfaz:  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 Si el componente se expone como un servicio web, el contrato de servicios correspondiente que se expone, y con el que los clientes deberán ser compatibles, es como sigue:  
  
```csharp
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
> El IID forma parte del espacio de nombres inicial del contrato.  
  
 Las aplicaciones cliente que utilizan este servicio deberán ser conformes a este contrato, así como utilizar un enlace compatible con el que se especificó en la configuración de la aplicación.  
  
 El siguiente ejemplo de código muestra un archivo de configuración predeterminado. Al ser un servicio Web de Windows Communication Foundation (WCF), se ajusta al esquema de configuración del modelo de servicio estándar y se puede editar de la misma manera que otros archivos de configuración de servicios WCF.  
  
 En las modificaciones típicas se incluye:  
  
- Cambiar la dirección del punto de conexión del formulario predeterminado ApplicationName/ComponentName/InterfaceName a un formulario más útil.  
  
- Modificar el espacio de nombres del servicio del formulario predeterminado `http://tempuri.org/InterfaceID` a un formulario más relevante.  
  
- Cambiar el punto de conexión para utilizar un enlace de transporte diferente.  
  
     En el caso de hospedaje en COM+, se utiliza el transporte de las canalizaciones con nombre de manera predeterminada, aunque en su lugar puede utilizarse un transporte fuera de equipo, tipo TCP.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Integración con aplicaciones COM+](integrating-with-com-plus-applications.md)
