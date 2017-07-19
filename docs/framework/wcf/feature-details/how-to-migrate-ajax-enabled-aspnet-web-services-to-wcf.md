---
title: "C&#243;mo migrar servicios web de ASP.NET con AJAX habilitado a WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# C&#243;mo migrar servicios web de ASP.NET con AJAX habilitado a WCF
En este tema se describen los procedimientos para migrar un  servicio de AJAX de ASP.NET básico a un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] de AJAX habilitado equivalente.  Muestra cómo crear una funcionalidad de la versión de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] equivalente de un servicio AJAX de ASP.NET.  Los dos servicios se pueden usar en paralelo o el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede usar para reemplazar el servicio de AJAX de ASP.NET.  
  
 Migrar un servicio de AJAX de ASP.NET existente a un servicio de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le proporciona las siguientes ventajas:  
  
-   Puede exponer su servicio de AJAX como un servicio SOAP con una configuración adicional mínima.  
  
-   Puede aprovecharse de las características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como el seguimiento, etc...  
  
 En los procedimientos siguientes se asume que está usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
 El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo que sigue a los procedimientos.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] exponer un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a través de un extremo habilitado para AJAX, consulte el tema [Uso de la configuración para agregar un extremo AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### Crear y probar la aplicación de servicio web ASP.NET  
  
1.  Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  En el menú **Archivo**, seleccione **Nuevo**, **Proyecto**, **Web**, y, a continuación, seleccione **Aplicación de servicio web ASP.NET**.  
  
3.  Asigne al proyecto el nombre `ASPHello` y haga clic en **Aceptar**.  
  
4.  Quite los comentarios de línea en el archivo Service1.asmx.cs que contiene `System.Web.Script.Services.ScriptService]` para habilitar AJAX en este servicio.  
  
5.  En el menú **Compilar**, seleccione **Compilar solución**.  
  
6.  En el menú **Depurar**, seleccione **Iniciar sin depurar**.  
  
7.  En la página web generada, seleccione la operación `HelloWorld`.  
  
8.  Haga clic en el botón **Invocar** en la página de prueba de `HelloWorld`.  Debería recibir la siguiente respuesta XML.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. Esta respuesta confirma que ha recibido un servicio de AJAX de ASP.NET que funciona y, en particular, que el servicio ha expuesto un extremo en Service1.asmx\/HelloWorld que responde a la solicitud HTTP POST y devuelve XML.  
  
     Ahora ya puede convertir este servicio para utilizar un servicio de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### Para crear una aplicación de servicio de AJAX de WCF equivalente.  
  
1.  Haga clic con el botón secundario en el proyecto **ASPHello** y seleccione **Agregar**, **Nuevo elemento**, y **Servicio WCF con AJAX habilitado**.  
  
2.  Denomine al servicio como `WCFHello` y haga clic en **Agregar**.  
  
3.  Abra el archivo WCFHello.svc.cs.  
  
4.  En Service1.asmx.cs, copie la siguiente implementación de la operación `HelloWorld`.  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  Pegue la implementación copiada de la operación `HelloWorld` en el archivo WCFHello.svc.cs en vez del código siguiente.  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  Especifique el atributo `Namespace` para <xref:System.ServiceModel.ServiceContractAttribute> como `WCFHello`.  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  Agregue <xref:System.ServiceModel.Web.WebInvokeAttribute> a la operación `HelloWorld` y establezca la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> para devolver <xref:System.ServiceModel.Web.WebMessageFormat>.  Observe que, si no se establece, el tipo devuelto predeterminado es <xref:System.ServiceModel.Web.WebMessageFormat>.  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  En el menú **Compilar**, seleccione **Compilar solución**.  
  
9. Abra al archivo WCFHello.svc.cs y en el menú **Depurar**, seleccione **Iniciar sin depurar**.  
  
10. El servicio expone un extremo en `WCFHello.svc/HelloWorld`, que responde a la solicitudes HTTP POST.  Las solicitudes HTTP POST no se pueden probar desde el explorador, pero los extremos devuelven XML a continuación de XML.  
  
    ```  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. Los extremos `WCFHello.svc/HelloWorld` y `Service1.aspx/HelloWorld` funcionan de forma equivalente.  
  
## Ejemplo  
 El código resultado del procedimiento descrito en este tema se proporciona en el ejemplo siguiente.  
  
```  
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
  
 El tipo <xref:System.Xml.XmlDocument> no es compatible con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque no es serializable por <xref:System.Xml.Serialization.XmlSerializer>.  Puede utilizar un tipo <xref:System.Xml.Linq.XDocument> o serializar <xref:System.Xml.XmlDocument.DocumentElement%2A> en su lugar.  
  
 Si los servicios web de ASMX se están actualizando y migrando, de manera paralela a los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], evite asignar dos tipos al mismo nombre en el cliente.  Esto produce una excepción en los serializadores si el mismo tipo se utiliza en <xref:System.Web.Services.WebMethodAttribute> y <xref:System.ServiceModel.ServiceContractAttribute>:  
  
-   Si se agrega primero el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], que invoca al método en el servicio web ASMX produce una excepción en <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> porque la definición de estilo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de orden en el proxy tiene prioridad.  
  
-   Si se agrega primero el servicio web ASMX, el método de invocación en el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produce una excepción en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> porque la definición de estilo del servicio web de orden en el proxy tiene prioridad.  
  
 Hay diferencias significativas en el comportamiento entre <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y el AJAX de ASP.NET <xref:System.Web.Script.Serialization.JavascriptSerializer>.  Por ejemplo, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> representa un diccionario como una matriz de pares clave\-valor, mientras que el <xref:System.Web.Script.Serialization.JavascriptSerializer> de AJAX de ASP.NET representa un diccionario como objetos JSON reales.  Por tanto lo siguiente es el diccionario representado en ASP.NET AJAX.  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add(“one”, 1);  
d.Add(“two”, 2);  
```  
  
 Este diccionario se representa en objetos JSON como se muestra en la siguiente lista:  
  
-   \[{"Clave":"uno","Valor":1}, {"Clave":"dos","Valor":2}\] por <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
  
-   {"uno":1, "dos":2} por el <xref:System.Web.Script.Serialization.JavascriptSerializer> de AJAX de ASP.NET  
  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> es más eficaz en el sentido de que puede controlar los diccionarios cuyo tipo de clave no es de cadena, mientras que <xref:System.Web.Script.Serialization.JavascriptSerializer> no puede.  Pero el último es más compatible con JSON.  
  
 Las diferencias significativas entre estos serializadores se resumen en la siguiente tabla.  
  
|Categoría de diferencias|DataContractJsonSerializer|JavaScriptSerializer de AJAX de ASP.NET|  
|------------------------------|--------------------------------|---------------------------------------------|  
|Deserializar el búfer vacío \(nuevo byte \[0\]\) en <xref:System.Object> \(o <xref:System.Uri> o algunas otras clases\).|SerializationException|null|  
|Serialización de <xref:System.DBNull.Value>|{} \(or {"\_\_type":"\#System"}\)|Null|  
|Serialización de los miembros privados de tipos \[Serializable\].|serialized|not serialized|  
|Serialización de las propiedades públicas de los tipos <xref:System.Runtime.Serialization.ISerializable>.|not serialized|serialized|  
|"Extensiones" de JSON|Conforme con la especificación de JSON, que requiere comillas en los nombres de miembro de objetos \({"a":"hola"}\).|Admite los nombres de miembros de objeto sin comillas \({a:"hola"}\).|  
|<xref:System.DateTime>Hora universal coordinada \(UTC\)|No admite el formato "\\\/Date\(123456789U\)\\\/" or "\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)".|Admite el formato "\\\/Date\(123456789U\)\\\/" y "\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)" como valores DateTime.|  
|Representación de diccionarios|Una matriz de KeyValuePair\<K,V\>, administra tipos clave que no son cadenas.|Como objetos JSON reales, pero solo controla los tipos clave que son cadenas.|  
|Caracteres con escape|Siempre con una barra diagonal de escape \(\/\); nunca permite caracteres de JSON no válidos sin escape, como "\\n".|Con una barra diagonal de escape \(\/\) para los valores DateTime .|  
  
## Vea también  
 [Uso de la configuración para agregar un extremo AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)