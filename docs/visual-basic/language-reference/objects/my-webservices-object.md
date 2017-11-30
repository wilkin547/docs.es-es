---
title: My.WebServices (Objeto)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords: My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a>My.WebServices (Objeto)
Proporciona propiedades para crear y obtener acceso a una sola instancia de cada servicio Web XML al que hace referencia el proyecto actual.  
  
## <a name="remarks"></a>Comentarios  
 El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual. Cada una de las instancias se crea a petición. Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`. El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad. Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web. Para obtener información sobre cómo agregar servicios Web a un proyecto, vea [obtiene acceso a los servicios de aplicaciones Web](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 La `My.WebServices` objeto expone sólo los servicios de Web asociados con el proyecto actual. No proporciona acceso a servicios Web declarados en archivos DLL que se hace referencia. Para obtener acceso a un servicio Web que proporciona un archivo DLL, debe usar el nombre completo del servicio Web, en el formulario *nombre dll*. *WebServiceName*. Para obtener más información, consulte [obtiene acceso a los servicios de aplicaciones Web](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto y sus propiedades no están disponibles para las aplicaciones Web.  
  
## <a name="properties"></a>Propiedades  
 Cada propiedad de la `My.WebServices` objeto proporciona acceso a una instancia de un servicio Web al que hace referencia el proyecto actual. El nombre de la propiedad es el mismo que el nombre del servicio Web que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de servicio Web.  
  
> [!NOTE]
>  Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un servicio Web es *RootNamespace*_*Namespace*\_*ServiceName*. Por ejemplo, considere dos servicios Web denominados `Service1`. Si uno de estos servicios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, podría tener acceso a ese servicio mediante `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Cuando acceda por primera vez una de las `My.WebServices` propiedades del objeto, crea una nueva instancia del servicio Web y lo almacena. Los accesos posteriores de esa propiedad devuelven esa instancia del servicio Web.  
  
 Puede desechar un servicio Web mediante la asignación de `Nothing` a la propiedad de ese servicio Web. Asigna el establecedor de propiedad `Nothing` al valor almacenado. Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.  
  
 Puede probar si una propiedad de la `My.WebServices` objeto almacena una instancia del servicio Web mediante la `Is` o `IsNot` operador. Puede usar los operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
>  Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación. Sin embargo, si la propiedad almacena actualmente `Nothing`, la propiedad se crea una nueva instancia del servicio Web y, a continuación, devuelve esa instancia. Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.WebServices` especial de objetos y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin modificar su valor.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo llama a la `FahrenheitToCelsius` método de la `TemperatureConverter` servicio Web XML y devuelve el resultado.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Para que funcione este ejemplo, el proyecto debe hacer referencia a un servicio Web denominado `Converter`, y que el servicio Web debe exponer el `ConvertTemperature` método. Para obtener más información, consulte [obtiene acceso a los servicios de aplicaciones Web](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
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
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [Acceso a los servicios web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
