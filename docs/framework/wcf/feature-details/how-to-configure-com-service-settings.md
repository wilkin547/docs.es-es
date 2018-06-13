---
title: Cómo configurar los parámetros de los servicios COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: 43964331f6728db0f094eaceb63e2c306d2dd3ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490109"
---
# <a name="how-to-configure-com-service-settings"></a>Cómo configurar los parámetros de los servicios COM+
Cuando se agrega o quita una interfaz de aplicaciones mediante la herramienta de configuración de servicio de COM+, la configuración del servicio web se actualiza en el archivo de configuración de la aplicación. En el modo hospedado de COM +, el archivo Application.config se coloca en el directorio raíz de la aplicación (%PROGRAMFILES%\ComPlus aplicaciones\\{appid} es el valor predeterminado). En cualquiera de los modos hospedados en la web, el archivo Web.config se encuentra en el directorio vroot especificado.  
  
> [!NOTE]
>  La utilización de la firma de los mensajes protege de la alteración de los mensajes entre el cliente y un servidor. Además, la utilización del cifrado en el nivel del mensaje o del transporte protege contra la divulgación de información de los mensajes entre un cliente y un servidor. Al igual que con los servicios de Windows Communication Foundation (WCF), debe usar la limitación para limitar el número de llamadas simultáneas, conexiones, instancias y las operaciones pendientes. Así se contribuye a evitar el consumo excesivo de recursos. El comportamiento del límite de peticiones se especifica mediante los valores del archivo de configuración del servicio.  
  
## <a name="example"></a>Ejemplo  
 Considere un componente que implementa la siguiente interfaz:  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 Si el componente se expone como un servicio web, el contrato de servicios correspondiente que se expone, y con el que los clientes deberán ser compatibles, es como sigue:  
  
```  
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
>  El IID forma parte del espacio de nombres inicial del contrato.  
  
 Las aplicaciones cliente que utilizan este servicio deberán ser conformes a este contrato, así como utilizar un enlace compatible con el que se especificó en la configuración de la aplicación.  
  
 El siguiente ejemplo de código muestra un archivo de configuración predeterminado. Que se va a un servicio Web de Windows Communication Foundation (WCF), esto es conforme al esquema de configuración de modelo de servicio estándar y se puede editar en la misma forma que otros archivos de configuración de servicios WCF.  
  
 En las modificaciones típicas se incluye:  
  
-   Cambiar la dirección del punto de conexión del formulario predeterminado ApplicationName/ComponentName/InterfaceName a un formulario más útil.  
  
-   Modificar el espacio de nombres del servicio desde el valor predeterminado "http://tempuri.org/InterfaceID" formulario a un formulario más relevante.  
  
-   Cambiar el punto de conexión para utilizar un enlace de transporte diferente.  
  
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
 [Integración en aplicaciones COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
