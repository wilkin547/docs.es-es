---
title: My.WebServices (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 0b63b44c2cd9d55094fb83fed6c04e4de528a25c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867205"
---
# <a name="mywebservices-object"></a>My.WebServices (Objeto)

Proporciona propiedades para crear y obtener acceso a una sola instancia de cada servicio Web XML al que hace referencia el proyecto actual.  
  
## <a name="remarks"></a>Comentarios  

 El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual. Cada una de las instancias se crea a petición. Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`. El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad. Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web. Para obtener información sobre cómo agregar servicios web a un proyecto, consulte [acceso a servicios Web de aplicaciones](../../developing-apps/programming/accessing-application-web-services.md).  
  
 El `My.WebServices` objeto expone solo los servicios web asociados al proyecto actual. No proporciona acceso a los servicios Web declarados en los archivos DLL a los que se hace referencia. Para tener acceso a un servicio Web que proporciona un archivo DLL, debe usar el nombre completo del servicio Web, con el formato *DllName*. *WebServiceName*. Para obtener más información, vea [acceso a servicios Web de aplicaciones](../../developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto y sus propiedades no están disponibles para las aplicaciones Web.  
  
## <a name="properties"></a>Propiedades  

 Cada propiedad del `My.WebServices` objeto proporciona acceso a una instancia de un servicio Web al que hace referencia el proyecto actual. El nombre de la propiedad es el mismo que el nombre del servicio Web al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del servicio Web.  
  
> [!NOTE]
> Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un servicio web es *RootNamespace*_*namespace* \_ *ServiceName*. Por ejemplo, considere dos servicios web denominados `Service1` . Si uno de estos servicios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1` , tendría acceso a ese servicio mediante `My.WebServices.WindowsApplication1_Namespace1_Service1` .  
  
 La primera vez que se obtiene acceso a una de las `My.WebServices` propiedades del objeto, se crea una nueva instancia del servicio Web y se almacena. Los accesos posteriores de esa propiedad devuelven esa instancia del servicio Web.  
  
 Puede eliminar un servicio Web asignando `Nothing` a la propiedad de ese servicio Web. El establecedor de propiedad `Nothing` se asigna al valor almacenado. Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.  
  
 Puede comprobar si una propiedad del `My.WebServices` objeto almacena una instancia del servicio Web mediante el `Is` `IsNot` operador o. Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing` .  
  
> [!NOTE]
> Normalmente, el `Is` `IsNot` operador o tiene que leer el valor de la propiedad para realizar la comparación. Sin embargo, si la propiedad almacena actualmente `Nothing` , la propiedad crea una nueva instancia del servicio Web y, a continuación, devuelve esa instancia. Sin embargo, el compilador Visual Basic trata las propiedades del objeto de forma `My.WebServices` especial y permite `Is` que el `IsNot` operador o Compruebe el estado de la propiedad sin modificar su valor.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se llama al `FahrenheitToCelsius` método del `TemperatureConverter` servicio Web XML y se devuelve el resultado.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Para que este ejemplo funcione, el proyecto debe hacer referencia a un servicio Web denominado `Converter` y ese servicio Web debe exponer el `ConvertTemperature` método. Para obtener más información, vea [acceso a servicios Web de aplicaciones](../../developing-apps/programming/accessing-application-web-services.md).  
  
 Este código no funciona en un proyecto de aplicación Web.  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="availability-by-project-type"></a>Disponibilidad por tipo de proyecto  
  
|Tipo de proyecto|Disponible|  
|---|---|  
|Aplicación Windows|**Sí**|  
|Biblioteca de clases|**Sí**|  
|Aplicación de consola|**Sí**|  
|Biblioteca de controles de Windows|**Sí**|  
|Biblioteca de controles web|**Sí**|  
|Servicio de Windows|**Sí**|  
|Sitio web|No|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Acceso a los servicios web de la aplicación](../../developing-apps/programming/accessing-application-web-services.md)
