---
title: Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 6114fa90b10a5d0cacb60a7ad40f63fae776e174
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683527"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF
En este tema se describe los procedimientos para migrar un servicio AJAX de ASP.NET básico a un servicio de Windows Communication Foundation (WCF) con AJAX habilitado equivalente. Muestra cómo crear una versión WCF funcionalmente equivalente de un servicio AJAX de ASP.NET. Los dos servicios, a continuación, se pueden usar en paralelo, o el servicio de WCF puede utilizarse para reemplazar el servicio de AJAX de ASP.NET.

 Migración de ASP.NET AJAX existente servicio a un servicio AJAX de WCF le ofrece las siguientes ventajas:

- Puede exponer su servicio de AJAX como un servicio SOAP con una configuración adicional mínima.

- Puede beneficiarse de las características WCF, como el seguimiento y así sucesivamente.

 Los procedimientos siguientes suponen que está usando Visual Studio 2012.

 El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo que sigue a los procedimientos.

 Para obtener más información acerca de cómo exponer un servicio WCF a través de un extremo con AJAX habilitado, consulte el [Cómo: Usar configuración para agregar un extremo ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) tema.

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Crear y probar la aplicación de servicio web ASP.NET

1. Abra Visual Studio 2012.

2. Desde el **archivo** menú, seleccione **New**, a continuación, **proyecto**, a continuación, **Web**y, a continuación, seleccione **aplicación de servicio Web de ASP.NET** .

3. Denomine el proyecto `ASPHello` y haga clic en **Aceptar**.

4. Quite los comentarios de línea en el archivo Service1.asmx.cs que contiene `System.Web.Script.Services.ScriptService]` para habilitar AJAX en este servicio.

5. Desde el **compilar** menú, seleccione **compilar solución**.

6. En el menú **Depurar**, seleccione **Iniciar sin depurar**.

7. En la página web generada, seleccione la operación `HelloWorld`.

8. Haga clic en el **Invoke** situado en la `HelloWorld` página de prueba. Debería recibir la siguiente respuesta XML.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Esta respuesta confirma que ha recibido un servicio de AJAX de ASP.NET que funciona y, en particular, que el servicio ha expuesto un punto de conexión en Service1.asmx/HelloWorld que responde a la solicitud HTTP POST y devuelve XML.

     Ahora está listo para convertir este servicio para utilizar un servicio AJAX de WCF.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Para crear una aplicación de servicio de AJAX de WCF equivalente.

1. Haga clic en el **ASPHello** del proyecto y seleccione **agregar**, a continuación, **nuevo elemento**y, a continuación, **servicio WCF habilitado para AJAX**.

2. Nombre del servicio `WCFHello` y haga clic en **agregar**.

3. Abra el archivo WCFHello.svc.cs.

4. En Service1.asmx.cs, copie la siguiente implementación de la `HelloWorld` operación.

    ```
    public string HelloWorld()
    {
         return "Hello World";
    }
    ```

5. Pegar implementación copiada de la `HelloWorld` operación en el archivo WCFHello.svc.cs en lugar de en el código siguiente.

    ```
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. Especifique el `Namespace` atributo <xref:System.ServiceModel.ServiceContractAttribute> como `WCFHello`.

    ```
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. Agregar el <xref:System.ServiceModel.Web.WebInvokeAttribute> a la `HelloWorld` operación y establezca el <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> propiedad para devolver <xref:System.ServiceModel.Web.WebMessageFormat.Xml>. Observe que, si no se establece, el tipo devuelto predeterminado es <xref:System.ServiceModel.Web.WebMessageFormat.Json>.

    ```
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. Desde el **compilar** menú, seleccione **compilar solución**.

9. Abra el archivo Wcfhello.svc.cs y desde el **depurar** menú, seleccione **iniciar sin depurar**.

10. El servicio expone un punto de conexión en `WCFHello.svc/HelloWorld`, que responde a solicitudes HTTP POST. Las solicitudes HTTP POST no se pueden probar desde el explorador, pero los puntos de conexión devuelven XML a continuación de XML.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. El `WCFHello.svc/HelloWorld` y `Service1.aspx/HelloWorld` puntos de conexión ahora son funcionalmente equivalentes.

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

 Si los servicios Web ASMX se están actualizando y migran en paralelo a los servicios WCF, evite asignar dos tipos en el mismo nombre en el cliente. Esto produce una excepción en los serializadores si el mismo tipo se utiliza en <xref:System.Web.Services.WebMethodAttribute> y <xref:System.ServiceModel.ServiceContractAttribute>:

- Si se agrega primero el servicio WCF, invocar el método de servicio Web ASMX produce una excepción en <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> porque la definición de estilo WCF del orden en el proxy tiene prioridad.

- Si primero se agrega el servicio Web ASMX, invocar el método en el servicio WCF produce una excepción en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque la definición de estilo del servicio Web del orden en el proxy tiene prioridad.

 Hay diferencias significativas en el comportamiento entre <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavaScriptSerializer>. Por ejemplo, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> representa un diccionario como una matriz de pares clave-valor, mientras que el <xref:System.Web.Script.Serialization.JavaScriptSerializer> de AJAX de ASP.NET representa un diccionario como objetos JSON reales. Por tanto lo siguiente es el diccionario representado en ASP.NET AJAX.

```
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Este diccionario se representa en objetos JSON como se muestra en la siguiente lista:

- [{"Clave":"uno","Valor":1}, {"Clave":"dos","Valor":2}] por <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

- {"uno": 1, "dos": 2} por el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> es más eficaz en el sentido de que puede controlar los diccionarios cuyo tipo de clave no es de cadena, mientras que <xref:System.Web.Script.Serialization.JavaScriptSerializer> no puede. Pero el último es más compatible con JSON.

 Las diferencias significativas entre estos serializadores se resumen en la siguiente tabla.

|Categoría de diferencias|DataContractJsonSerializer|JavaScriptSerializer de AJAX de ASP.NET|
|-----------------------------|--------------------------------|---------------------------------------|
|Deserializar el búfer vacío (nuevo byte [0]) en <xref:System.Object> (o <xref:System.Uri> o algunas otras clases).|SerializationException|nulo|
|Serialización de <xref:System.DBNull.Value>|{} (o {"__type": "#System"})|Null|
|Serialización de los miembros privados de tipos [Serializable].|serialized|not serialized|
|Serialización de las propiedades públicas de los tipos <xref:System.Runtime.Serialization.ISerializable>.|not serialized|serialized|
|"Extensiones" de JSON|Conforme con la especificación de JSON, que requiere comillas en los nombres de miembro de objetos ({"a":"hola"}).|Admite los nombres de miembros de objeto sin comillas ({a:"hola"}).|
|<xref:System.DateTime>Hora universal coordinada (UTC)|No es compatible con el formato "\\/Date(123456789U)\\/" o "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".|Admite el formato "\\/Date(123456789U)\\/" y "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "como valores de fecha y hora.|
|Representación de diccionarios|Una matriz de KeyValuePair\<K, V >, administra tipos clave que no son cadenas.|Como objetos JSON reales, pero solo controla los tipos clave que son cadenas.|
|Caracteres con escape|Siempre con una barra diagonal de escape (/); nunca permite caracteres de JSON no válidos sin escape, como "\n".|Con una barra diagonal de escape (/) para los valores DateTime .|

## <a name="see-also"></a>Vea también

- [Cómo: Usar la configuración para agregar un extremo de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
