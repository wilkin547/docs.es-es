---
title: Uso del moniker de WCF con clientes COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: c1d5e0c7d7460e207fedba601e991f25281ddb6e
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202082"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Uso del moniker de WCF con clientes COM
Este ejemplo muestra cómo utilizar el moniker de servicio de Windows Communication Foundation (WCF) para integrar los servicios web en entornos de desarrollo basados en COM, como Microsoft Office Visual Basic para Aplicaciones (Office VBA) o Visual Basic 6,0. El ejemplo está compuesto por un cliente de Windows Script Host (.vbs), una biblioteca de cliente auxiliar (.dll) y una biblioteca de servicios (.dll) hospedados en Internet Information Services (IIS). El servicio es un servicio de calculadora y el cliente COM llama operaciones matemáticas: Sumar, Restar, Multiplicar y Dividir, en el servicio. La actividad Client está visible en las ventanas de cuadro de mensaje.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 El servicio implementa un contrato `ICalculator` definido como se muestra en el ejemplo de código siguiente:  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 El ejemplo muestra los tres enfoques alternativos para utilizar el moniker:  
  
- Contrato con tipo: el contrato se registra como un tipo visible COM en el equipo cliente.  
  
- Contrato de WSDL: el contrato se proporciona en forma de documento WSDL.  
  
- Contrato de intercambio de metadatos: el contrato se recupera en tiempo de ejecución a partir de un punto de conexión de intercambio de metadatos (MEX).  
  
## <a name="typed-contract"></a>Contrato con tipo  
 Para utilizar el moniker con un uso del contrato con tipo, los tipos apropiadamente atribuidos para el contrato de servicios se deben registrar con COM. En primer lugar, se debe generar un cliente mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Ejecute el comando siguiente desde un símbolo del sistema en el directorio del cliente para generar el proxy especificado.  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 Esta clase debe estar incluida en un proyecto y el proyecto se debería configurar para generar un ensamblado firmado visible en COM al compilarse. El atributo siguiente debería incluirse en el archivo AssemblyInfo.cs.  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 Después de compilar el proyecto, registre los tipos visibles en COM mediante `regasm`, como se muestra en el siguiente ejemplo.  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 El ensamblado que se crea se debería agregar a la caché global de ensamblados. Aunque no estrictamente necesario, esto simplifica el proceso del tiempo de ejecución localizando el ensamblado. El comando siguiente agrega el ensamblado en la caché global de ensamblados.  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> El moniker de servicio requiere solo el registro del tipo y no utiliza el proxy para comunicarse con el servicio.  
  
 La aplicación cliente ComCalcClient.vbs utiliza la función `GetObject` para construir un proxy para el servicio, utilizando la sintaxis del moniker del servicio para especificar la dirección, enlace y contrato para el servicio.  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 Los parámetros utilizados por el moniker especifican:  
  
- La dirección del punto de conexión de servicio.  
  
- El enlace que el cliente debería utilizar para conectar con ese punto de conexión. En este caso se utiliza el wsHttpBinding definido por el sistema aunque se pueden definir enlaces personalizados en archivos de configuración del cliente. Para el uso con Windows Scripting Host, el enlace personalizado se define en un archivo Cscript.exe.config en el mismo directorio que Cscript.exe.  
  
- El tipo del contrato que se admite en el extremo. Éste es el tipo que se generó y se registró anteriormente. Dado que Visual Basic Script no proporciona un entorno COM fuertemente tipado, se debe especificar un identificador para el contrato. Este GUID es `interfaceID` de CalcProxy.tlb, que se puede ver utilizando herramientas COM como el Visor de Objetos OLE/COM(OleView.exe). En entornos fuertemente tipados como Office VBA o Visual Basic 6,0, se puede usar la adición de una referencia explícita a la biblioteca de tipos y, a continuación, la declaración del tipo del objeto proxy en lugar del parámetro de contrato. Esto también proporciona la compatibilidad IntelliSense durante el desarrollo de la aplicación cliente.  
  
 Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con tipo para comunicarse con un servicio WCF. A pesar del uso de COM en la aplicación cliente, la comunicación con el servicio está solo compuesto por las llamadas del Servicio Web.  
  
## <a name="wsdl-contract"></a>Contrato WSDL  
 No se exigen ningún registro de biblioteca de cliente para utilizar el moniker con un contrato WSDL, pero el contrato WSDL para el servicio se debe recuperar a través de un mecanismo fuera de banda, como utilizar un explorador para tener acceso al punto de conexión WSDL para el servicio. El moniker puede tener acceso entonces a ese contrato en el tiempo de ejecución.  
  
 La aplicación cliente ComCalcClient.vbs utiliza `FileSystemObject` para tener acceso al archivo WSDL guardado localmente y, a continuación, usa de nuevo la función `GetObject` para construir un proxy para el servicio.  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 Los parámetros utilizados por el moniker especifican:  
  
- La dirección del punto de conexión de servicio.  
  
- El enlace que el cliente debería utilizar para conectarse con ese punto de conexión y el espacio de nombres en el que se define ese enlace. En este caso, se usa `wsHttpBinding_ICalculator`.  
  
- El WSDL que define el contrato. En este caso ésta es la cadena leída del archivo serviceWsdl.xml.  
  
- El nombre y espacio de nombres del contrato. Se requiere esta identificación porque el WSDL puede contener más de un contrato.  
  
    > [!NOTE]
    > De forma predeterminada, los servicios WCF generan archivos WSDL independientes para cada espacio de nombres que use. Éstos se vinculan con el uso de la construcción de importación de WSDL. Dado que el moniker espera una definición WSDL única, el servicio debe utilizar un espacio de nombres único como se muestra en este ejemplo o los archivos independientes deben estar combinados manualmente.  
  
 Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con un contrato WSDL para comunicarse con un servicio WCF.  
  
## <a name="metadata-exchange-contract"></a>Contrato de Intercambio de Metadatos  
 Para utilizar el moniker con un contrato MEX, como con el contrato WSDL, no se requiere ningún registro del cliente. El contrato para el servicio se recupera en el tiempo de ejecución a través del uso interno de Intercambio de Metadatos.  
  
 La aplicación cliente ComCalcClient.vbs utiliza de nuevo la función `GetObject` para construir un proxy para el servicio.  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 Los parámetros utilizados por el moniker especifican:  
  
- La dirección del punto de conexión de intercambio de metadatos del servicio.  
  
- La dirección del punto de conexión de servicio.  
  
- El enlace que el cliente debería utilizar para conectarse con ese punto de conexión y el espacio de nombres en el que se define ese enlace. En este caso, se usa `wsHttpBinding_ICalculator`.  
  
- El nombre y espacio de nombres del contrato. Se requiere esta identificación porque el WSDL puede contener más de un contrato.  
  
 Al haber construido la instancia del proxy con el moniker de servicio, la aplicación cliente puede llamar a los métodos en el proxy, lo que hace que la infraestructura del moniker de servicio llame a las operaciones de servicio correspondientes.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Al ejecutar el ejemplo, la respuesta de la operación se muestra en una ventana de cuadro de mensaje de Windows Script Host. Esto muestra un cliente COM que realiza llamadas COM utilizando el moniker con un contrato MEX para comunicarse con un servicio WCF.  
  
#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. En una Símbolo del sistema para desarrolladores para Visual Studio, abra la carpeta \client\bin\, en la carpeta específica del lenguaje.  
  
    > [!NOTE]
    > Si usa Windows Vista, Windows Server 2008, Windows 7 o Windows Server 2008 R2, asegúrese de ejecutar el símbolo del sistema con privilegios de administrador.  
  
4. Escriba `tlbexp.exe client.dll /out:CalcProxy.tlb` para exportar el archivo DLL a un archivo TLB. Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.  
  
5. Escriba `regasm.exe /tlb:CalcProxy.tlb client.dll` para registrar los tipos con com. Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.  
  
6. Escriba `gacutil.exe /i client.dll` para agregar el ensamblado a la caché global de ensamblados.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1. Pruebe que puede tener acceso al servicio mediante un explorador escribiendo la siguiente dirección: `http://localhost/servicemodelsamples/service.svc` . Como respuesta se debe mostrar una página de confirmación.  
  
2. Ejecute ComCalcClient.vbs desde \client, en la carpeta específica del lenguaje. La actividad del cliente se muestra en ventanas de cuadro de mensaje.  
  
3. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. En el equipo del servicio, cree un directorio virtual denominado ServiceModelSamples. El script Setupvroot.bat incluido con el ejemplo se puede utilizar para crear el directorio de disco y el directorio virtual.  
  
2. Copie los archivos de programa del servicio del directorio %SystemDrive%\Inetpub\wwwroot\servicemodelsamples al directorio virtual ServiceModelSamples del equipo de servicio. Asegúrese de incluir los archivos en el directorio \bin.  
  
3. Copie el archivo de script de cliente de la carpeta \client, en la carpeta específica del lenguaje, al equipo cliente.  
  
4. En el archivo de script, cambie el valor de la dirección de la definición del punto de conexión para que coincida con la nueva dirección de su servicio. Reemplace cualquier referencia a "localhost" con un nombre de dominio completo en la dirección.  
  
5. Copie el archivo WSDL al equipo cliente. En el archivo WSDL, serviceWsdl.xml, reemplace cualquier referencia al "host local" con un nombre de dominio completo en la dirección.  
  
6. Copie la biblioteca Client.dll de la carpeta \client\bin\, en la carpeta específica del lenguaje, a un directorio en el equipo cliente.  
  
7. Desde un símbolo del sistema, navegue a ese directorio de destino en el equipo cliente. Si usa Windows Vista o Windows Server 2008, asegúrese de ejecutar el símbolo del sistema como administrador.  
  
8. Escriba `tlbexp.exe client.dll /out:CalcProxy.tlb` para exportar el archivo DLL a un archivo TLB. Es posible que se produzca una "Advertencia de exportador de biblioteca de tipos", pero no es un problema, porque no se requiere el tipo genérico.  
  
9. Escriba `regasm.exe /tlb:CalcProxy.tlb client.dll` para registrar los tipos con com. Asegúrese de que la ruta de acceso se ha establecido en la carpeta que contiene `regasm.exe` antes de ejecutar el comando.  
  
10. Escriba `gacutil.exe /i client.dll` para agregar el ensamblado a la caché global de ensamblados. Asegúrese de que la ruta de acceso se ha establecido en la carpeta que contiene `gacutil.exe` antes de ejecutar el comando.  
  
11. Compruebe que puede tener acceso al servicio desde el equipo cliente utilizando un explorador.  
  
12. En el equipo cliente, inicie ComCalcClient.vbs.  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Por razones de seguridad, quite la definición del directorio virtual y los permisos concedidos en los pasos de instalación cuando haya acabado con los ejemplos.  
