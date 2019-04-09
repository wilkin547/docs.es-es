---
title: Control de errores
ms.date: 03/30/2017
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
ms.openlocfilehash: da2ae3db0ff0432a49fcbf6de674bfb730be1286
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136440"
---
# <a name="error-handling"></a>Control de errores
## <a name="error-handling-in-windows-communication-foundation"></a>Error de control en Windows Communication Foundation  
 Cuando un servicio detecta una excepción o error inesperados, hay varias maneras de diseñar una solución desde el control de excepciones. Aunque no es único "correcta" o "recomendable" control de errores solución, hay varias rutas de acceso válidas a considerar. Normalmente, se recomienda implementar una solución híbrida que combine varios enfoques de la lista siguiente, según la complejidad de la implementación de WCF, el tipo y la frecuencia de las excepciones, el controlado frente a la naturaleza no controlada de la las excepciones y cualquier traza, registro o los requisitos de directiva.  
  
 Estas soluciones se explican en más profundidad en el resto de esta sección.  
  
### <a name="the-microsoft-enterprise-library"></a>Biblioteca de Microsoft Enterprise  
 El bloque de la aplicación de control de excepciones de la biblioteca de empresas de Microsoft ayuda a implementar patrones comunes de diseño y a crear una estrategia coherente para procesar las excepciones que aparecen en todos los niveles arquitectónicos de una aplicación empresarial. Está diseñado para admitir el código estándar contenido en instrucciones CATCH en componentes de aplicación. En lugar de repetir este código (como código que registra la información de excepción) en bloques catch idénticos en una aplicación, el bloque de la aplicación de control de excepciones permite a los desarrolladores encapsulen esta lógica como controlador de excepciones reutilizables.  
  
 Esta biblioteca incluye un controlador de excepciones de contrato de error predefinido. Este controlador de excepciones está diseñado para usarse en los límites de servicio de (Windows® Communication Foundation (WCF), y genera un nuevo Contrato de errores desde la excepción.  
  
 Los bloques de aplicación tienen por objeto escribir prácticas recomendadas y proporcionar un enfoque común para el control de excepciones en la aplicación. Además, los controladores de errores personalizados y los contratos de error desarrollados por uno mismo pueden resultar muy útiles. Por ejemplo, controladores de errores personalizados proporcionan una oportunidad excelente para promover automáticamente todas las excepciones a FaultExceptions y también para agregar capacidades de registro a la aplicación.  
  
 Para obtener más información, consulte [Microsoft Enterprise Library](https://docs.microsoft.com/previous-versions/msp-n-p/ff632023(v=pandp.10)).  
  
### <a name="dealing-with-expected-exceptions"></a>Tratar excepciones esperadas  
 El curso de acción adecuado consiste en detectar excepciones esperadas en cada operación o punto de extensibilidad relevante, decidir si se puede recuperar y devolver el error personalizado apropiado en un Faultexceptiont\<T >  
  
### <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>Tratar excepciones no esperadas con un IErrorHandler  
 Para tratar las excepciones inesperadas, el curso de acción recomendado es "enlazar" un IErrorHandler. Los controladores de errores solo capturan excepciones en el nivel de tiempo de ejecución WCF (la capa "modelo de servicio"), no en el nivel del canal. La única forma de enlazar un IErrorHandler en el nivel de canal es crear un canal personalizado, que no se recomienda en la mayoría de los escenarios.  
  
 Una "excepción inesperada" suele ser una excepción irrecuperable ni una excepción de procesamiento; en su lugar, es una excepción inesperada de usuario. Una excepción irrecuperable (como una excepción de memoria insuficiente): la suele controlar la [controlador de excepciones de modelo de servicio](xref:System.ServiceModel.Dispatcher.ExceptionHandler) automáticamente: no se puede controlar correctamente y la única razón para controlar la excepción nada puede ser realice un registro adicional o para devolver una excepción estándar al cliente. Aparece una excepción de procesamiento en el procesamiento de mensajes, (por ejemplo, en la serialización, el codificador o el nivel formateador, normalmente no se pueden controlar en un IErrorHandler, pues suele ser demasiado antiguo o demasiado atrasado para que intervenga el controlador de errores en el momento en que estas excepciones aparecen. De forma similar, las excepciones de transporte no se pueden controlar en un IErrorHandler.  
  
 Con un IErrorHandler, puede controlar explícitamente el comportamiento de la aplicación cuando se produce una excepción. Puede:  
  
1.  Decida si enviar o no un error al cliente  
  
2.  Reemplazar una excepción con un error  
  
3.  Reemplazar un error con otro error  
  
4.  Realizar el registro o el seguimiento  
  
5.  Realizar otras actividades personalizadas  
  
 Se puede instalar en un controlador de errores personalizado agregándolo a la propiedad ErrorHandlers de distribuidores de canal para el servicio.  Es posible tener varias llamadas a un controlador de errores y se les llama en el orden en que se agregan a esta colección.  
  
 IErrorHandler.ProvideFault controla el mensaje de error que se envía al cliente. Se llama a este método independientemente del tipo de excepción iniciado por una operación del servicio. Si no se realiza ninguna operación aquí, WCF supone su comportamiento predeterminado y continúa como si no hubiera controladores de errores personalizado en su lugar.  
  
 Un área que podría quizás usar este enfoque es cuando se desea crear un sitio central para convertir las excepciones en errores antes de enviarlos al cliente (asegurando que la instancia no está dispuesta y el canal no se desplaza el estado Faulted).  
  
 El método IErrorHandler.HandleError normalmente se usa para implementar comportamientos relacionados con errores, como registro de errores, notificaciones del sistema, cierre de aplicaciones, etc. IErrorHandler.HandleError se puede llamar en lugares diferentes dentro del servicio y, en función de dónde se produzca el error, el mismo subproceso que la operación puede llamar o no al método HandleError; no hay ninguna garantía al respecto.  
  
### <a name="dealing-with-exceptions-outside-wcf"></a>Tratar excepciones esperadas fuera de WCF  
 A menudo, excepciones de configuración, excepciones de la cadena de conexión a bases de datos y otras excepciones similares pueden aparecer en el contexto de una aplicación de WCF, pero no son excepciones iniciadas por consultas del modelo de servicio o servicio web en sí. Estas excepciones son excepciones "normales" externas al servicio web y deben controlarse como son otras excepciones externas en el entorno para que lo administre.  
  
### <a name="tracing-exceptions"></a>Traza de excepciones  
 El seguimiento es el lugar de sólo "catch-all", donde se podrían ver todas las excepciones. Para obtener más información acerca de excepciones de seguimiento e inicio de sesión, vea Seguimiento e Inicio de sesión.  
  
### <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>Errores de la plantilla del URI al usar WebGetAttribute y WebInvokeAttribute  
 Los atributos WebGet y WebInvoke permiten especificar una plantilla URI que asigna los componentes de la solicitud a los parámetros de la operación. Por ejemplo, la plantilla de URI "weather/{state}/{city}" asigna la solicitud en tokens literales, un parámetro denominado estado y un parámetro denominado ciudad. Estos parámetros se pueden enlazar a continuación por nombre a algunos de los parámetros formales de la operación.  
  
 Los parámetros de plantilla aparecen en forma de cadena del URI mientras que los parámetros formales de un contrato tipo pueden ser de tipos de no cadena. Por consiguiente, una conversión debe realizarse antes que la operación que se invoca. Un [tabla de conversión de formatos](wcf-web-http-programming-model-overview.md) está disponible.  
  
 Sin embargo, si la conversión genera un error, no se puede hacer saber a la operación qué ha salido mal. La conversión de tipo, en cambio, emerge en forma de error de envío.  
  
 Un error de envío de conversión de tipo se puede inspeccionar igual que muchos otros tipos de errores de envío instalando un controlador de errores. El punto de extensibilidad de IErrorHandler se llama para controlar excepciones de nivel de servicio. Desde allí se puede elegir la respuesta que se va a devolver al que llama, así como realizar las tareas personalizadas y de envío de informes.  
  
## <a name="see-also"></a>Vea también

- [Programación básica de WCF](../basic-wcf-programming.md)
