---
title: 'Cómo: Hospedar un flujo de trabajo no perteneciente al servicio en IIS'
ms.date: 03/30/2017
ms.assetid: f362562c-767d-401b-8257-916616568fd4
ms.openlocfilehash: 70fd6aca94f2addd7ee568e897171ae1da86db67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496770"
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a>Cómo: Hospedar un flujo de trabajo no perteneciente al servicio en IIS
Los flujos de trabajo que no sean servicios de flujo de trabajo se pueden hospedar en IIS/WAS. Esto es útil cuando deba hospedar un flujo de trabajo escrito por otra persona. Por ejemplo, si hospeda en otro host el diseñador de flujo de trabajo y permite a los usuarios que creen sus propios flujos de trabajo.  Si se hospedan flujos de trabajo no pertenecientes al servicio en IIS, se proporciona compatibilidad con características como el reciclaje de proceso, el apagado por inactividad, la supervisión del estado de los procesos y la activación basada en mensajes. Los servicios de flujo de trabajo hospedados en IIS contienen actividades de la clase <xref:System.ServiceModel.Activities.Receive> y se activan cuando IIS recibe un mensaje. Los flujos de trabajo no pertenecientes al servicio no contienen actividades de mensajería y no se pueden activar enviando un mensaje de forma predeterminada.  Debe derivar una clase de la clase <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> y definir un contrato de servicio que contenga operaciones para crear una instancia de flujo de trabajo. Este tema le guiará a través de la creación de un flujo de trabajo simple, definir un contrato de servicio que un cliente puede utilizar para activar el flujo de trabajo y derivar una clase de <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> que utiliza el contrato de servicio para escuchar las solicitudes de creación de flujo de trabajo.  
  
### <a name="create-a-simple-workflow"></a>Crear un flujo de trabajo simple  
  
1.  Cree una nueva solución de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vacía denominada `CreationEndpointTest`.  
  
2.  Agregue un nuevo proyecto de aplicación de servicio de flujo de trabajo WCF denominado `SimpleWorkflow` a la solución. Se abrirá el diseñador de flujo de trabajo.  
  
3.  Elimine las actividades ReceiveRequest y SendResponse. Estas actividades son las que convierten un flujo de trabajo en un servicio de flujo de trabajo. Puesto que no estamos trabajando con un servicio de flujo de trabajo, ya no las necesitamos.  
  
4.  Establezca el valor de DisplayName para la actividad de secuencia a "Flujo de trabajo secuencial".  
  
5.  Cambie el nombre de Service1.xamlx a Workflow1.xamlx.  
  
6.  Haga clic en el diseñador fuera de la actividad de secuencia y establezca las propiedades Name y ConfigurationName en "Workflow1"  
  
7.  Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la clase <xref:System.Activities.Statements.Sequence>. El <xref:System.Activities.Statements.WriteLine> actividad puede encontrarse en el **primitivas** sección del cuadro de herramientas. Establecer el <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad de la <xref:System.Activities.Statements.WriteLine> actividad a "Hola, mundo".  
  
     El flujo de trabajo ahora debe tener la misma apariencia que la del siguiente diagrama.  
  
     ![Un flujo de trabajo simple](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")  
  
### <a name="create-the-workflow-creation-service-contract"></a>Crear el contrato de servicio de creación del flujo de trabajo  
  
1.  Agregue un nuevo proyecto de biblioteca de clases denominado `Shared` a la solución `CreationEndpointTest`.  
  
2.  Agregue una referencia a System.ServiceModel.dll, System.Configuration y System.ServiceModel.Activities al proyecto `Shared`.  
  
3.  Cambie el nombre del archivo Class1.cs a IWorkflowCreation.cs y agregue el siguiente código al archivo.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     Este contrato define dos operaciones que crean una nueva instancia de flujo de trabajo no perteneciente al servicio que acaba de crear. Una crea una nueva instancia con un identificador de instancia generado y la otra permite especificar el identificador de instancia de la nueva instancia de flujo de trabajo.  Ambos métodos permiten pasar parámetros a la nueva instancia de flujo de trabajo. Este contrato lo expondrá la <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> para permitir a los clientes crear nuevas instancias de un flujo de trabajo no pertenecientes al servicio.  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a>Derivar una clase de WorkflowHostingEndpoint  
  
1.  Agregue una nueva clase denominada `CreationEndpoint` deriva <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> a la `Shared` proyecto.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  Agregue una variable de la clase <xref:System.Uri> estática local denominada `defaultBaseUri` a la clase `CreationEndpoint`.  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  Agregue el siguiente constructor a la clase `CreationEndpoint`. Observe que especificamos el contrato de servicio `IWorkflowCreation` en la llamada al constructor base.  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  Agregue el siguiente constructor predeterminado a la clase `CreationEndpoint`.  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  Agregue una propiedad `DefaultBaseUri` estática a la clase `CreationEndpoint`. Esta propiedad se usará para contener un URI base predeterminado si no se proporciona ninguno.  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  Cree el siguiente método para obtener el enlace predeterminado con el fin de usarlo para el extremo de creación.  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  Invalide el método <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> para devolver el identificador de instancia de flujo de trabajo. Si el `Action` termina de encabezado en "Create" devuelve un GUID vacío, si la `Action` encabezado termina con "createwithinstanceid", devuelve el GUID pasado al método. De lo contrario, se produce una excepción <xref:System.InvalidOperationException>. Estos encabezados `Action` corresponden a las dos operaciones definidas en el contrato de servicio `IWorkflowCreation`.  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  Invalide el método <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> para crear una clase <xref:System.ServiceModel.Activities.WorkflowCreationContext> y agregar los argumentos del flujo de trabajo, enviar el identificador de instancia al cliente y, a continuación, devolver la clase <xref:System.ServiceModel.Activities.WorkflowCreationContext>.  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a>Crear un elemento de extremo estándar para que pueda configurar WorkflowCreationEndpoint  
  
1.  Agregue una referencia a Shared en el proyecto `CreationEndpoint`  
  
2.  Agregue una nueva clase denominada `CreationEndpointElement` derivada de la clase <xref:System.ServiceModel.Configuration.StandardEndpointElement> al proyecto `CreationEndpoint`. Esta clase representará una clase `CreationEndpoint` en un archivo web.config.  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  Agregue una propiedad denominada `EndpointType` para devolver el tipo de extremo.  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  Invalide el método <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> y devuelva un nuevo `CreationEndpoint`.  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  Sobrecargue los métodos <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> y <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>. Estos métodos solo se deben definir, no necesitan que se les agregue código.  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  Agregue la clase de colección de `CreationEndpoint` al archivo CreationEndpointElement.cs del proyecto `CreationEndpoint`. Esta clase se usa durante la configuración para contener muchas instancias de `CreationEndpoint` en un archivo web.config.  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  Compile la solución.  
  
### <a name="host-the-workflow-in-iis"></a>Hospede el flujo de trabajo en IIS  
  
1.  Cree una nueva aplicación denominada `MyCreationEndpoint` en IIS.  
  
2.  Copie el archivo workflow1.xaml generado por el diseñador de flujo de trabajo en el directorio de la aplicación y cámbiele el nombre a workflow1.xamlx.  
  
3.  Copie los archivos shared.dll y CreationEndpoint.dll en el directorio \bin de la aplicación. Cree este directorio si no está presente.  
  
4.  Reemplace el contenido de archivo Web.config del proyecto `CreationEndpoint` por el código siguiente.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  A continuación del elemento `<system.web>`, registre `CreationEndpoint` agregando el siguiente código de configuración.  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     De esta forma, se registra la clase `CreationEndpointCollection` para que pueda configurar una clase `CreationEndpoint` en un archivo web.config.  
  
6.  Agregar un `<service>` elemento (después de la \</extensions > etiqueta) con un `CreationEndpoint` que escuchará los mensajes entrantes.  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  Agregar un \<comportamientos > elemento (después de la  \< /servicios > etiqueta) para habilitar los metadatos del servicio.  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  Copie el archivo web.config en el directorio de la aplicación IIS.  
  
9. Prueba para ver si el extremo de creación funciona Iniciando Internet Explorer y vaya a http://localhost/MyCreationEndpoint/Workflow1.xamlx. Internet Explorer debe mostrar la siguiente pantalla:  
  
     ![Probar el servicio](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a>Crear un cliente que llamará a CreationEndpoint.  
  
1.  Agregue una nueva aplicación de consola a la solución `CreationEndpointTest`.  
  
2.  Agregue  referencias a System.ServiceModel.dll, System.ServiceModel.Activities y al proyecto `Shared`.  
  
3.  En el `Main` método crea un <xref:System.ServiceModel.ChannelFactory%601> de tipo `IWorkflowCreation` y llame a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. De esta forma, se devolverá un proxy. Después, puede llamar a `Create` en ese proxy para crear una instancia de flujo de trabajo hospedad en IIS:  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  Ejecute CreationEndpointClient. La salida debe tener un aspecto parecido al siguiente:  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  No verá la salida del flujo de trabajo porque se está ejecutando en IIS, que no tiene salida de la consola.  
  
## <a name="example"></a>Ejemplo  
 Este es el código completo de este ejemplo.  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 Este ejemplo puede parecer confuso porque el usuario nunca implementa ningún servicio que implemente `IWorkflowCreation`. La razón es que `CreationEndpoint` lo hace automáticamente.  
  
## <a name="see-also"></a>Vea también  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Instrucciones de hospedaje de Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [Arquitectura de Windows Workflow](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [Reanudación del marcador WorkflowHostingEndpoint](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [Rehospedaje del Diseñador de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Información general de Windows Workflow](../../../../docs/framework/windows-workflow-foundation/overview.md)
