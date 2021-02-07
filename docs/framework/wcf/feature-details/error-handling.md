---
description: 'Más información sobre: control de errores en Windows Communication Foundation (WCF)'
title: Control de errores
ms.date: 03/30/2017
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
ms.openlocfilehash: e09c07037e2b3398e2f82307242032a29c356ce5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704776"
---
# <a name="error-handling-in-windows-communication-foundation-wcf"></a>Control de errores en Windows Communication Foundation (WCF)

Cuando un servicio detecta una excepción o error inesperados, hay varias maneras de diseñar una solución desde el control de excepciones. Aunque no hay una única solución de control de errores "correcta" o "procedimiento recomendado", hay varias rutas de acceso válidas que se deben tener en cuenta. Normalmente se recomienda implementar una solución híbrida que combine varios enfoques de la lista siguiente, en función de la complejidad de la implementación de WCF, el tipo y la frecuencia de las excepciones, la naturaleza administrada frente a no controlada de las excepciones y cualquier seguimiento, registro o requisito de directiva asociado.

Estas soluciones se explican en más profundidad en el resto de esta sección.

## <a name="the-microsoft-enterprise-library"></a>Biblioteca de Microsoft Enterprise

El bloque de la aplicación de control de excepciones de la biblioteca de empresas de Microsoft ayuda a implementar patrones comunes de diseño y a crear una estrategia coherente para procesar las excepciones que aparecen en todos los niveles arquitectónicos de una aplicación empresarial. Está diseñado para admitir el código estándar contenido en instrucciones CATCH en componentes de aplicación. En lugar de repetir este código (como código que registra la información de excepción) en bloques catch idénticos en una aplicación, el bloque de la aplicación de control de excepciones permite a los desarrolladores encapsulen esta lógica como controlador de excepciones reutilizables.

Esta biblioteca incluye un controlador de excepciones de contrato de error predefinido. Este controlador de excepciones está diseñado para su uso en los límites del servicio WCF y genera un nuevo contrato de error a partir de la excepción.

Los bloques de aplicación tienen por objeto escribir prácticas recomendadas y proporcionar un enfoque común para el control de excepciones en la aplicación. Además, los controladores de errores personalizados y los contratos de error desarrollados por uno mismo pueden resultar muy útiles. Por ejemplo, controladores de errores personalizados proporcionan una oportunidad excelente de promover automáticamente todas las excepciones a FaultExceptions y también para agregar capacidades de inicio de sesión a la aplicación.

Para obtener más información, consulte [Microsoft Enterprise Library](/previous-versions/msp-n-p/ff632023(v=pandp.10)).

## <a name="dealing-with-expected-exceptions"></a>Tratar las excepciones esperadas

El curso de acción adecuado es detectar las excepciones esperadas en cada operación o punto de extensibilidad relevante, decidir si se pueden recuperar y devolver el error personalizado adecuado en un FaultException \<T> .
  
## <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>Tratar las excepciones inesperadas mediante un IErrorHandler

Para tratar las excepciones inesperadas, el curso de acción recomendado es "enlazar" un IErrorHandler. Los controladores de error solo detectan excepciones en el nivel de tiempo de ejecución de WCF (el nivel de "modelo de servicio"), no en el nivel de canal. La única forma de enlazar un IErrorHandler en el nivel de canal es crear un canal personalizado, que no se recomienda en la mayoría de los escenarios.

Una "excepción inesperada" no suele ser una excepción irrecuperable ni una excepción de procesamiento; en su lugar, se trata de una excepción de usuario inesperada. Una excepción irrecuperable (como una excepción de memoria insuficiente), que normalmente la controla el controlador de [excepciones del modelo de servicio](xref:System.ServiceModel.Dispatcher.ExceptionHandler) , no se puede controlar de forma automática y la única razón para controlar este tipo de excepción puede ser el registro adicional o devolver una excepción estándar al cliente. Aparece una excepción de procesamiento en el procesamiento de mensajes, (por ejemplo, en la serialización, el codificador o el nivel formateador, normalmente no se pueden controlar en un IErrorHandler, pues suele ser demasiado antiguo o demasiado atrasado para que intervenga el controlador de errores en el momento en que estas excepciones aparecen. De forma similar, las excepciones de transporte no se pueden controlar en un IErrorHandler.

Con un IErrorHandler, puede controlar explícitamente el comportamiento de la aplicación cuando se produce una excepción. Puede hacer lo siguiente:  

1. Decida si desea enviar o no un error al cliente.

2. Reemplace una excepción con un error.

3. Reemplace un error por otro error.

4. Realizar el registro o el seguimiento.

5. Realizar otras actividades personalizadas.

Se puede instalar en un controlador de errores personalizado agregándolo a la propiedad ErrorHandlers de distribuidores de canal para el servicio.  Es posible tener varias llamadas a un controlador de errores y se les llama en el orden en que se agregan a esta colección.

IErrorHandler.ProvideFault controla el mensaje de error que se envía al cliente. Se llama a este método independientemente del tipo de excepción iniciado por una operación del servicio. Si no se realiza ninguna operación aquí, WCF asume su comportamiento predeterminado y continúa como si no hubiera ningún controlador de errores personalizado en su lugar.

Un área que podría quizás usar este enfoque es cuando se desea crear un sitio central para convertir las excepciones en errores antes de enviarlos al cliente (asegurando que la instancia no está dispuesta y el canal no se desplaza el estado Faulted).

El método IErrorHandler. HandleError se usa normalmente para implementar comportamientos relacionados con errores, como el registro de errores, las notificaciones del sistema, el cierre de la aplicación, etc. Se puede llamar a IErrorHandler. HandleError en varios lugares dentro del servicio y, en función de dónde se produzca el error, el método HandleError puede ser invocado o no por el mismo subproceso que la operación. no se realiza ninguna garantía en este sentido.

## <a name="dealing-with-exceptions-outside-wcf"></a>Tratar las excepciones fuera de WCF

A menudo, excepciones de configuración, excepciones de la cadena de conexión a bases de datos y otras excepciones similares pueden aparecer en el contexto de una aplicación de WCF, pero no son excepciones iniciadas por consultas del modelo de servicio o servicio web en sí. Estas excepciones son excepciones "normales" externas al servicio Web y se deben controlar de la misma forma que se administrarán otras excepciones externas en el entorno.

## <a name="tracing-exceptions"></a>Traza de excepciones

El seguimiento es el único lugar "comodín" en el que se pueden ver todas las excepciones. Para obtener más información acerca de excepciones de seguimiento e inicio de sesión, vea Seguimiento e Inicio de sesión.

## <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>Errores de la plantilla del URI al usar WebGetAttribute y WebInvokeAttribute

Los atributos WebGet y WebInvoke permiten especificar una plantilla URI que asigna los componentes de la solicitud a los parámetros de la operación. Por ejemplo, la plantilla de URI "weather/{state}/{city}" asigna la solicitud en tokens literales, un parámetro denominado estado y un parámetro denominado ciudad. Estos parámetros se pueden enlazar a continuación por nombre a algunos de los parámetros formales de la operación.

Los parámetros de plantilla aparecen en forma de cadena del URI mientras que los parámetros formales de un contrato tipo pueden ser de tipos de no cadena. Por consiguiente, una conversión debe realizarse antes que la operación que se invoca. Hay disponible una [tabla de formatos de conversión](wcf-web-http-programming-model-overview.md) .

Sin embargo, si la conversión genera un error, no se puede hacer saber a la operación qué ha salido mal. La conversión de tipo, en cambio, emerge en forma de error de envío.

Un error de envío de conversión de tipo se puede inspeccionar igual que muchos otros tipos de errores de envío instalando un controlador de errores. El punto de extensibilidad de IErrorHandler se llama para controlar excepciones de nivel de servicio. Desde allí se puede elegir la respuesta que se va a devolver al que llama, así como realizar las tareas personalizadas y de envío de informes.

## <a name="see-also"></a>Vea también

- [Programación básica de WCF](../basic-wcf-programming.md)
