---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 9123167e0f97592592765f7b4a4aa768064fc173
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596609"
---
# <a name="customchannelstester"></a>CustomChannelsTester
El `CustomChannelsTester` es una herramienta que se utiliza para probar las implementaciones del canal personalizadas contra un conjunto de contratos de servicios predefinidos. Puede seleccionar el conjunto de contratos de servicios y pasarlo a la herramienta utilizando un archivo XML. La herramienta genera a continuación el servicio y el cliente que ejerce sus implementaciones del canal personalizadas durante el intercambio de mensajes.  
  
### <a name="to-build-the-tool"></a>Para compilar la herramienta  
  
1. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
2. Al compilar la solución, se generan tres archivos: CustomChannelsTester.exe, TestSpec.xml y SampleRun.cmd. El archivo SampleRun. cmd tiene una línea de comandos de ejemplo que muestra cómo usar esta herramienta para probar el ejemplo [Transport: UDP](transport-udp.md) .  
  
### <a name="to-run-the-tool"></a>Para ejecutar la herramienta  
  
- Escriba el siguiente comando en el símbolo del sistema:  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Se requiere utilizar la opción `/binding`.  
  
     `/dll`es necesario si "Binding" no es un enlace proporcionado por el sistema proporcionado por Windows Communication Foundation (WCF).  
  
     `/testspec` es opcional.  
  
     Esto crea el servidor y los clientes basados en las características técnicas de pruebas y el enlace.  
  
     Ejecuta el cliente y el servidor y devuelve los resultados.  
  
     A continuación, se muestra el ejemplo XML para la descripción de las características técnicas de pruebas (testspec.xml):  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>
    <!-- Test a sessionful / sessionless contract-->
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
