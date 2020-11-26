---
title: Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 89c9601ba6afcef9733d7653564a98664a1ed70f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241907"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF

En este tema se describen los procedimientos para migrar un servicio básico de AJAX de ASP.NET a un servicio equivalente compatible con AJAX Windows Communication Foundation (WCF). Muestra cómo crear una versión de WCF funcionalmente equivalente de un servicio de AJAX de ASP.NET. Los dos servicios se pueden usar en paralelo, o el servicio WCF se puede usar para reemplazar el servicio ASP.NET AJAX.

 La migración de un servicio de ASP.NET AJAX existente a un servicio de AJAX de WCF proporciona las siguientes ventajas:

- Puede exponer su servicio de AJAX como un servicio SOAP con una configuración adicional mínima.

- Puede beneficiarse de las características de WCF como el seguimiento, etc.

 En los procedimientos siguientes se supone que usa Visual Studio 2012.

 El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo que sigue a los procedimientos.

 Para obtener más información acerca de cómo exponer un servicio WCF a través de un punto de conexión habilitado para AJAX, vea el tema [How to: Use Configuration to Add a ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) .

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Crear y probar la aplicación de servicio web ASP.NET

1. Abra Visual Studio 2012.

2. En el menú **archivo** , seleccione **nuevo**, **proyecto**, **Web** y, a continuación, seleccione **aplicación de servicio Web ASP.net**.

3. Asigne un nombre al proyecto `ASPHello` y haga clic en **Aceptar**.

4. Quite los comentarios de línea en el archivo Service1.asmx.cs que contiene `System.Web.Script.Services.ScriptService]` para habilitar AJAX en este servicio.

5. En el menú **compilar** , seleccione **compilar solución**.

6. En el menú **Depurar**, seleccione **Iniciar sin depuración**.

7. En la página web generada, seleccione la operación `HelloWorld`.

8. Haga clic en el botón **invocar** en la `HelloWorld` Página de prueba. Debería recibir la siguiente respuesta XML.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Esta respuesta confirma que ha recibido un servicio de AJAX de ASP.NET que funciona y, en particular, que el servicio ha expuesto un punto de conexión en Service1.asmx/HelloWorld que responde a la solicitud HTTP POST y devuelve XML.

     Ahora está listo para convertir este servicio para utilizar un servicio de AJAX de WCF.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Para crear una aplicación de servicio de AJAX de WCF equivalente.

1. Haga clic con el botón derecho en el proyecto **ASPHello** y seleccione **Agregar**, **nuevo elemento** y, a continuación, **servicio WCF habilitado para Ajax**.

2. Asigne un nombre al servicio `WCFHello` y haga clic en **Agregar**.

3. Abra el archivo WCFHello.svc.cs.

4. En Service1.asmx.cs, copie la siguiente implementación de la `HelloWorld` operación.

    ```csharp
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

5. Pegue la implementación copiada de la `HelloWorld` operación en el archivo WCFHello.SVC.CS en lugar del código siguiente.

    ```csharp
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. Especifique el `Namespace` atributo <xref:System.ServiceModel.ServiceContractAttribute> como `WCFHello` .

    ```csharp
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. Agregue <xref:System.ServiceModel.Web.WebInvokeAttribute> a la `HelloWorld` operación y establezca la <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> propiedad en devuelta <xref:System.ServiceModel.Web.WebMessageFormat.Xml> . Observe que, si no se establece, el tipo devuelto predeterminado es <xref:System.ServiceModel.Web.WebMessageFormat.Json>.

    ```csharp
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. En el menú **compilar** , seleccione **compilar solución**.

9. Abra el archivo WCFHello. SVC y, en el menú **depurar** , seleccione **iniciar sin depurar**.

10. El servicio ahora expone un punto de conexión en `WCFHello.svc/HelloWorld` , que responde a las solicitudes HTTP POST. Las solicitudes HTTP POST no se pueden probar desde el explorador, pero los puntos de conexión devuelven XML a continuación de XML.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. Los `WCFHello.svc/HelloWorld` extremos y `Service1.aspx/HelloWorld` son funcionalmente equivalentes.

## <a name="example"></a>Ejemplo

 El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo siguiente.

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 El tipo <xref:System.Xml.XmlDocument> no es compatible con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque no es serializable por <xref:System.Xml.Serialization.XmlSerializer>. Puede utilizar un tipo <xref:System.Xml.Linq.XDocument> o serializar <xref:System.Xml.XmlDocument.DocumentElement%2A> en su lugar.

 Si los servicios web ASMX se van a actualizar y migrar en paralelo a los servicios WCF, evite asignar dos tipos al mismo nombre en el cliente. Esto produce una excepción en los serializadores si el mismo tipo se utiliza en <xref:System.Web.Services.WebMethodAttribute> y <xref:System.ServiceModel.ServiceContractAttribute>:

- Si primero se agrega el servicio WCF, al invocar el método en el servicio Web ASMX se produce una excepción en <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> porque la definición de estilo WCF del orden en el proxy tiene prioridad.

- Si el servicio Web ASMX se agrega primero, al invocar el método en el servicio WCF se produce una excepción en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque la definición de estilo de servicio Web del orden en el proxy tiene prioridad.

 Hay diferencias significativas en el comportamiento entre <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavaScriptSerializer>. Por ejemplo, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> representa un diccionario como una matriz de pares clave-valor, mientras que el <xref:System.Web.Script.Serialization.JavaScriptSerializer> de AJAX de ASP.NET representa un diccionario como objetos JSON reales. Por tanto lo siguiente es el diccionario representado en ASP.NET AJAX.

```csharp
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Este diccionario se representa en objetos JSON como se muestra en la siguiente lista:

- [{"Clave":"uno","Valor":1}, {"Clave":"dos","Valor":2}] por <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

- {"uno": 1, "dos": 2} por ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> es más eficaz en el sentido de que puede controlar los diccionarios cuyo tipo de clave no es de cadena, mientras que <xref:System.Web.Script.Serialization.JavaScriptSerializer> no puede. Pero el último es más compatible con JSON.

 Las diferencias significativas entre estos serializadores se resumen en la siguiente tabla.

|Categoría de diferencias|DataContractJsonSerializer|JavaScriptSerializer de AJAX de ASP.NET|
|-----------------------------|--------------------------------|---------------------------------------|
|Deserializar el búfer vacío (nuevo byte [0]) en <xref:System.Object> (o <xref:System.Uri> o algunas otras clases).|SerializationException|null|
|Serialización de <xref:System.DBNull.Value>|{} (o {"__type": "#System"})|Null|
|Serialización de los miembros privados de tipos [Serializable].|serialized|not serialized|
|Serialización de las propiedades públicas de los tipos <xref:System.Runtime.Serialization.ISerializable>.|not serialized|serialized|
|"Extensiones" de JSON|Conforme con la especificación de JSON, que requiere comillas en los nombres de miembro de objetos ({"a":"hola"}).|Admite los nombres de miembros de objeto sin comillas ({a:"hola"}).|
|<xref:System.DateTime>Hora universal coordinada (UTC)|No admite el formato " \\ /Date (123456789U) \\ /" o " \\ /Date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ]))? \\ ) \\ \\ /)".|Admite el formato " \\ /Date (123456789U) \\ /" y " \\ /Date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ]))? \\ ) \\ \\ /) "como valores DateTime.|
|Representación de diccionarios|Una matriz de KeyValuePair \<K,V> , controla los tipos de clave que no son cadenas.|Como objetos JSON reales, pero solo controla los tipos clave que son cadenas.|
|Caracteres con escape|Siempre con una barra diagonal de escape (/); nunca permite caracteres de JSON no válidos sin escape, como "\n".|Con una barra diagonal de escape (/) para los valores DateTime .|

## <a name="see-also"></a>Vea también

- [Procedimiento para usar la configuración para agregar un punto de conexión AJAX de ASP.NET](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
