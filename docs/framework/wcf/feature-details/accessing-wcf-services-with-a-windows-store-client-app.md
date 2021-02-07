---
description: 'Más información sobre: acceso a servicios WCF con una aplicación cliente de la tienda Windows'
title: Obtener acceso a los servicios WCF con una aplicación cliente de la Tienda Windows
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: 6586b07e72749b0c136072474c27c264568ed3f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705413"
---
# <a name="access-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="0bbee-103">Acceder a servicios WCF con una aplicación cliente de la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0bbee-103">Access WCF Services with a Windows Store Client App</span></span>

<span data-ttu-id="0bbee-104">Windows 8 presenta un nuevo tipo de aplicaciones denominadas aplicaciones de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="0bbee-104">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="0bbee-105">Estas aplicaciones están diseñadas para una interfaz de pantalla táctil.</span><span class="sxs-lookup"><span data-stu-id="0bbee-105">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="0bbee-106">.NET Framework 4.5 permite que las aplicaciones de la Tienda Windows llamen a servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="0bbee-106">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="0bbee-107">Compatibilidad de WCF en aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0bbee-107">WCF Support in Windows Store Applications</span></span>  

 <span data-ttu-id="0bbee-108">Un subconjunto de funcionalidad de WCF está disponible en una aplicación de la Tienda Windows; vea las secciones siguientes para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="0bbee-108">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0bbee-109">Use las API de distribución de WinRT en lugar de las expuestas por WCF.</span><span class="sxs-lookup"><span data-stu-id="0bbee-109">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="0bbee-110">Para obtener más información, vea [API de distribución de WinRT](xref:Windows.Web.Syndication)</span><span class="sxs-lookup"><span data-stu-id="0bbee-110">For more information see, [WinRT Syndication API](xref:Windows.Web.Syndication)</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0bbee-111">No se admite el uso de Agregar referencia de servicio para agregar una referencia de servicio Web a un componente de Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="0bbee-111">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn't supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="0bbee-112">Enlaces admitidos</span><span class="sxs-lookup"><span data-stu-id="0bbee-112">Supported Bindings</span></span>  

 <span data-ttu-id="0bbee-113">Los siguientes enlaces de WCF se admiten en aplicaciones de la Tienda Windows:</span><span class="sxs-lookup"><span data-stu-id="0bbee-113">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="0bbee-114">Los elementos de enlace siguientes se admiten en aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0bbee-114">The following binding elements are supported in Windows Store Applications</span></span>  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="0bbee-115">Se admiten las codificaciones de texto y binarias.</span><span class="sxs-lookup"><span data-stu-id="0bbee-115">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="0bbee-116">Se admiten todos los modos de transferencia de WCF.</span><span class="sxs-lookup"><span data-stu-id="0bbee-116">All WCF transfer modes are supported.</span></span> <span data-ttu-id="0bbee-117">Para obtener más información, vea [Streaming Message Transfer](streaming-message-transfer.md).</span><span class="sxs-lookup"><span data-stu-id="0bbee-117">For more information see, [Streaming Message Transfer](streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="0bbee-118">Agregar referencia de servicio</span><span class="sxs-lookup"><span data-stu-id="0bbee-118">Add Service Reference</span></span>  

 <span data-ttu-id="0bbee-119">Para llamar a un servicio WCF desde una aplicación de la Tienda Windows, use la característica Agregar referencia de servicio de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="0bbee-119">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="0bbee-120">Observará algunos cambios en la funcionalidad de Agregar referencia de servicio cunado se lleva a cabo desde una aplicación de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="0bbee-120">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="0bbee-121">Primero no se genera ningún archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0bbee-121">First no configuration file is generated.</span></span> <span data-ttu-id="0bbee-122">Las aplicaciones de la Tienda Windows no usan archivos de configuración, por lo que deben configurarse en el código.</span><span class="sxs-lookup"><span data-stu-id="0bbee-122">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="0bbee-123">Este código de configuración se puede encontrar en el archivo References.cs que genera Agregar referencia de servicio.</span><span class="sxs-lookup"><span data-stu-id="0bbee-123">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="0bbee-124">Para ver este archivo, asegúrese de seleccionar "Mostrar todos los archivos" en el explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="0bbee-124">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="0bbee-125">El archivo se encuentra en los nodos Referencias de servicio y Reference.svcmap en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0bbee-125">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="0bbee-126">Todas las operaciones generadas para los servicios WCF en una aplicación de la Tienda Windows serán asincrónicas mediante el patrón asincrónico basado en tareas.</span><span class="sxs-lookup"><span data-stu-id="0bbee-126">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="0bbee-127">Para obtener más información, vea [tareas asincrónicas: simplificar la programación asincrónica con tareas](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span><span class="sxs-lookup"><span data-stu-id="0bbee-127">For more information, see [Async Tasks - Simplify Asynchronous Programming with Tasks](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span></span>  
  
 <span data-ttu-id="0bbee-128">Debido a que la configuración ahora se genera en el código, cualquier cambio realizado en el archivo Reference.cs se sobrescribirá cada vez que se actualice la referencia de servicio.</span><span class="sxs-lookup"><span data-stu-id="0bbee-128">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="0bbee-129">Para solucionar esta situación, el código de configuración se genera en un método parcial, que puede implementar en la clase de proxy cliente.</span><span class="sxs-lookup"><span data-stu-id="0bbee-129">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="0bbee-130">El método parcial se declara de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0bbee-130">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="0bbee-131">Puede implementar este método parcial y cambiar el enlace o el extremo en la clase de proxy de cliente de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bbee-131">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="0bbee-132">Serialización</span><span class="sxs-lookup"><span data-stu-id="0bbee-132">Serialization</span></span>  

 <span data-ttu-id="0bbee-133">Los siguientes serializadores se admiten en aplicaciones de la Tienda Windows:</span><span class="sxs-lookup"><span data-stu-id="0bbee-133">The following serializers are supported in Windows Store applications:</span></span>  
  
1. <span data-ttu-id="0bbee-134">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="0bbee-134">DataContractSerializer</span></span>  
  
2. <span data-ttu-id="0bbee-135">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="0bbee-135">DataContractJsonSerializer</span></span>  
  
3. <span data-ttu-id="0bbee-136">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="0bbee-136">XmlSerializer</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0bbee-137">XmlDictionaryWriter.Write(DateTime) ahora escribe el objeto DateTime como una cadena.</span><span class="sxs-lookup"><span data-stu-id="0bbee-137">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="0bbee-138">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0bbee-138">Security</span></span>  

<span data-ttu-id="0bbee-139">En las aplicaciones de la tienda Windows se admiten los siguientes modos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="0bbee-139">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="0bbee-140">En las aplicaciones de la tienda Windows se admiten los siguientes tipos de credenciales de cliente:</span><span class="sxs-lookup"><span data-stu-id="0bbee-140">The following client credential types are supported in Windows Store applications:</span></span>
  
1. <span data-ttu-id="0bbee-141">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0bbee-141">None</span></span>  
  
2. <span data-ttu-id="0bbee-142">Básico</span><span class="sxs-lookup"><span data-stu-id="0bbee-142">Basic</span></span>  
  
3. <span data-ttu-id="0bbee-143">Digest</span><span class="sxs-lookup"><span data-stu-id="0bbee-143">Digest</span></span>  
  
4. <span data-ttu-id="0bbee-144">Negotiate</span><span class="sxs-lookup"><span data-stu-id="0bbee-144">Negotiate</span></span>  
  
5. <span data-ttu-id="0bbee-145">NTLM</span><span class="sxs-lookup"><span data-stu-id="0bbee-145">NTLM</span></span>  
  
6. <span data-ttu-id="0bbee-146">Windows</span><span class="sxs-lookup"><span data-stu-id="0bbee-146">Windows</span></span>  
  
7. <span data-ttu-id="0bbee-147">Nombre de usuario (seguridad de mensaje)</span><span class="sxs-lookup"><span data-stu-id="0bbee-147">Username (Message Security)</span></span>  
  
8. <span data-ttu-id="0bbee-148">Windows (seguridad de transporte)</span><span class="sxs-lookup"><span data-stu-id="0bbee-148">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="0bbee-149">Para que las aplicaciones de la Tienda Windows tengan acceso y envíen las credenciales de Windows predeterminadas, debe habilitar esta funcionalidad en el archivo Package.appmanifest.</span><span class="sxs-lookup"><span data-stu-id="0bbee-149">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="0bbee-150">Abra este archivo y seleccione la pestaña capacidades y seleccione "credenciales de Windows predeterminadas".</span><span class="sxs-lookup"><span data-stu-id="0bbee-150">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="0bbee-151">Esto permite que la aplicación se conecte a recursos de la intranet que necesitan credenciales de dominio.</span><span class="sxs-lookup"><span data-stu-id="0bbee-151">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0bbee-152">Para que las aplicaciones de la tienda Windows realicen llamadas entre equipos, debe habilitar otra función denominada "redes domésticas o de trabajo".</span><span class="sxs-lookup"><span data-stu-id="0bbee-152">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="0bbee-153">Esta configuración también se encuentra en el archivo package. AppManifest en la pestaña capacidades. Active la casilla Home/Work networking.</span><span class="sxs-lookup"><span data-stu-id="0bbee-153">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="0bbee-154">Esto proporciona a la aplicación acceso entrante y saliente a las redes de los sitios de confianza del usuario, como casa y el trabajo.</span><span class="sxs-lookup"><span data-stu-id="0bbee-154">This gives your application inbound and outbound access to the networks of the user's trusted places like home and work.</span></span> <span data-ttu-id="0bbee-155">Los puertos críticos de entrada siempre se bloquean.</span><span class="sxs-lookup"><span data-stu-id="0bbee-155">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="0bbee-156">Para tener acceso a servicios de Internet también debe habilitar la capacidad de Internet (cliente).</span><span class="sxs-lookup"><span data-stu-id="0bbee-156">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="0bbee-157">Varios</span><span class="sxs-lookup"><span data-stu-id="0bbee-157">Misc</span></span>  

 <span data-ttu-id="0bbee-158">El uso de las clases siguientes se admite para las aplicaciones de la Tienda Windows:</span><span class="sxs-lookup"><span data-stu-id="0bbee-158">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="0bbee-159">Definir contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="0bbee-159">Defining Service Contracts</span></span>  

 <span data-ttu-id="0bbee-160">Se recomienda definir solo operaciones de servicio asincrónicas mediante el patrón asincrónico basado en tareas.</span><span class="sxs-lookup"><span data-stu-id="0bbee-160">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="0bbee-161">Esto garantiza que las aplicaciones de la Tienda Windows sigan respondiendo mientras se llama a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="0bbee-161">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0bbee-162">Aunque no se producirá ninguna excepción si define una operación sincrónica, se recomienda definir solamente operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="0bbee-162">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="0bbee-163">Llamar a servicios WCF desde aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0bbee-163">Calling WCF Services from Windows Store Applications</span></span>  

 <span data-ttu-id="0bbee-164">Como se mencionó antes, toda la configuración se debe hacer en el código en el método GetBindingForEndpoint de la clase de proxy generada.</span><span class="sxs-lookup"><span data-stu-id="0bbee-164">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="0bbee-165">La llamada a una operación de servicio se realiza igual que la llamada a cualquier método asincrónico basado en tareas, tal como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bbee-165">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="0bbee-166">Observe el uso de la palabra clave async en el método que realiza la llamada asincrónica y la palabra clave await al llamar al método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="0bbee-166">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbee-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bbee-167">See also</span></span>

- [<span data-ttu-id="0bbee-168">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="0bbee-168">Programming WCF Security</span></span>](programming-wcf-security.md)
- [<span data-ttu-id="0bbee-169">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0bbee-169">Bindings</span></span>](../bindings.md)
