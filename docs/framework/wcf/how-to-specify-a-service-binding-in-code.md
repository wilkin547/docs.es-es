---
title: Procedimiento para especificar un enlace de servicio en el código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236486"
---
# <a name="how-to-specify-a-service-binding-in-code"></a>Procedimiento para especificar un enlace de servicio en el código

En este ejemplo, se define un contrato de `ICalculator` para un servicio de la calculadora, el servicio se implementa en la clase `CalculatorService` y a continuación, su extremo se define mediante código, donde se especifica que el servicio debe utilizar la clase <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código. Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio. Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.  
  
 Para obtener una descripción de cómo configurar este servicio mediante elementos de configuración en lugar de código, consulte [Cómo: especificar un enlace de servicio en la configuración](how-to-specify-a-service-binding-in-configuration.md).  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a>Para especificar mediante código que se use BasicHttpBinding para el servicio  
  
1. Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Implemente el contrato de servicios en una clase de servicio.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. En la aplicación de alojamiento, cree la dirección base que han de utilizar el servicio y el enlace con el servicio.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Cree el host para el servicio, agregue el extremo y, a continuación, abra el host.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a>Para modificar los valores predeterminados de las propiedades de enlace  
  
1. Para modificar uno de los valores predeterminados de propiedades de la clase <xref:System.ServiceModel.BasicHttpBinding>, establezca el valor de propiedad del enlace en el nuevo valor antes de crear el host. Por ejemplo, para cambiar los valores predeterminados de tiempos de espera de apertura y cierre de 1 a 2 minutos, utilice lo siguiente.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Utilización de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)
- [Especificación de una dirección de punto de conexión](specifying-an-endpoint-address.md)
