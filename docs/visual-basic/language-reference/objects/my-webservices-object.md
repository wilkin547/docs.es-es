---
title: My. WebServices (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: c887f9b7c5a41c0aa02016354c46d5507b103d25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918178"
---
# <a name="mywebservices-object"></a>My.WebServices (Objeto)
Proporciona propiedades para crear y obtener acceso a una sola instancia de cada servicio Web XML al que hace referencia el proyecto actual.  
  
## <a name="remarks"></a>Comentarios  
 El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual. Cada una de las instancias se crea a petición. Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`. El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad. Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web. Para obtener información sobre cómo agregar servicios web a un proyecto, consulte [acceso a servicios Web de aplicaciones](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El `My.WebServices` objeto expone solo los servicios web asociados al proyecto actual. No proporciona acceso a los servicios Web declarados en los archivos DLL a los que se hace referencia. Para tener acceso a un servicio Web que proporciona un archivo DLL, debe usar el nombre completo del servicio Web, con el formato *DllName*. *WebServiceName*. Para obtener más información, vea [acceso a servicios Web de aplicaciones](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto y sus propiedades no están disponibles para las aplicaciones Web.  
  
## <a name="properties"></a>Properties (Propiedades)  
 Cada propiedad del `My.WebServices` objeto proporciona acceso a una instancia de un servicio Web al que hace referencia el proyecto actual. El nombre de la propiedad es el mismo que el nombre del servicio Web al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del servicio Web.  
  
> [!NOTE]
> Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un servicio web es *RootNamespace*_*namespace*\_*ServiceName*. Por ejemplo, considere dos servicios web denominados `Service1`. Si uno de estos servicios está en el espacio de `WindowsApplication1` nombres raíz y en `Namespace1`el espacio de nombres, tendría `My.WebServices.WindowsApplication1_Namespace1_Service1`acceso a ese servicio mediante.  
  
 La primera vez que se obtiene acceso `My.WebServices` a una de las propiedades del objeto, se crea una nueva instancia del servicio Web y se almacena. Los accesos posteriores de esa propiedad devuelven esa instancia del servicio Web.  
  
 Puede eliminar un servicio Web asignando `Nothing` a la propiedad de ese servicio Web. El establecedor de propiedad `Nothing` se asigna al valor almacenado. Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.  
  
 Puede comprobar si una propiedad del `My.WebServices` objeto almacena una instancia del servicio Web mediante el `Is` operador o `IsNot` . Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
> Normalmente, el `Is` operador `IsNot` o tiene que leer el valor de la propiedad para realizar la comparación. Sin embargo, si la propiedad almacena `Nothing`actualmente, la propiedad crea una nueva instancia del servicio Web y, a continuación, devuelve esa instancia. Sin embargo, el compilador Visual Basic trata las `My.WebServices` propiedades del objeto de forma especial `Is` y `IsNot` permite que el operador o Compruebe el estado de la propiedad sin modificar su valor.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se `FahrenheitToCelsius` llama al método `TemperatureConverter` del servicio Web XML y se devuelve el resultado.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Para que este ejemplo funcione, el proyecto debe hacer referencia a un servicio `Converter`Web denominado y ese servicio Web debe exponer `ConvertTemperature` el método. Para obtener más información, vea [acceso a servicios Web de aplicaciones](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Este código no funciona en un proyecto de aplicación Web.  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="availability-by-project-type"></a>Disponibilidad por tipo de proyecto  
  
|Tipo de proyecto|Disponible|  
|---|---|  
|Aplicación Windows|**Sí**|  
|Biblioteca de clases|**Sí**|  
|Aplicación de consola|**Sí**|  
|Biblioteca de controles de Windows|**Sí**|  
|Biblioteca de controles Web|**Sí**|  
|Servicio de Windows|**Sí**|  
|Sitio web|Sin|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Acceso a los servicios web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
