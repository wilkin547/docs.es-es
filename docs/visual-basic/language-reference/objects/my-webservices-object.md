---
title: My.WebServices (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: a60f32c4f581e42f240fca55ce496776c5511ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050296"
---
# <a name="mywebservices-object"></a>My.WebServices (Objeto)
Proporciona propiedades para crear y tener acceso a una sola instancia de cada servicio Web XML al que hace referencia el proyecto actual.  
  
## <a name="remarks"></a>Comentarios  
 El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual. Cada una de las instancias se crea a petición. Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`. El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad. Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web. Para obtener información sobre cómo agregar servicios Web a un proyecto, vea [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 La `My.WebServices` objeto expone sólo los servicios de Web asociados al proyecto actual. No proporciona acceso a servicios Web declarados en archivos DLL que se hace referencia. Para obtener acceso a un servicio Web que proporciona un archivo DLL, debe usar el nombre completo del servicio Web, en el formulario *DllName*. *WebServiceName*. Para obtener más información, consulte [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto y sus propiedades no están disponibles para las aplicaciones Web.  
  
## <a name="properties"></a>Propiedades  
 Cada propiedad de la `My.WebServices` objeto proporciona acceso a una instancia de un servicio Web al que hace referencia el proyecto actual. El nombre de la propiedad es el mismo que el nombre del servicio Web que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de servicio Web.  
  
> [!NOTE]
>  Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un servicio Web es *RootNamespace*_*Namespace*\_*ServiceName*. Por ejemplo, considere dos servicios Web denominados `Service1`. Si uno de estos servicios es el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, accedería a ese servicio mediante el uso de `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Cuando acceda por primera vez uno de los `My.WebServices` propiedades del objeto, crea una nueva instancia del servicio Web y lo almacena. Los accesos posteriores de esa propiedad devuelven esa instancia del servicio Web.  
  
 Puede eliminar de un servicio Web mediante la asignación `Nothing` a la propiedad de ese servicio Web. Asigna el establecedor de propiedad `Nothing` al valor almacenado. Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.  
  
 Puede probar si una propiedad de la `My.WebServices` objeto almacena una instancia del servicio Web mediante el uso de la `Is` o `IsNot` operador. Puede usar estos operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
>  Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación. Sin embargo, si la propiedad se almacena actualmente `Nothing`, la propiedad crea una nueva instancia del servicio Web y, a continuación, devuelve esa instancia. Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.WebServices` especialmente de objetos y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin cambiar su valor.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo llama a la `FahrenheitToCelsius` método de la `TemperatureConverter` servicio Web XML y devuelve el resultado.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Para que funcione este ejemplo, el proyecto debe hacer referencia a un servicio Web denominado `Converter`, y ese servicio Web debe exponer la `ConvertTemperature` método. Para obtener más información, consulte [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
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
|Sitio web|No|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Acceso a los servicios web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
