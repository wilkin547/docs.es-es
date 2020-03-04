---
title: Contenedor al que se puede llamar en tiempo de ejecución
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, COM wrappers
- RCW
- COM wrappers
- runtime callable wrappers
- interoperation with unmanaged code, COM wrappers
ms.assetid: 7e542583-1e31-4e10-b523-8cf2f29cb4a4
ms.openlocfilehash: 0b448379fba965060fdf3bf067e65374f40d1fc2
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156015"
---
# <a name="runtime-callable-wrapper"></a>Contenedor al que se puede llamar en tiempo de ejecución
Common Language Runtime expone objetos COM mediante un proxy denominado el contenedor RCW (Runtime Callable Wrapper). Aunque el contenedor RCW aparece como un objeto corriente para los clientes .NET, su función principal es calcular referencias de llamadas entre un cliente .NET y un objeto COM.  
  
 CLR crea exactamente un contenedor RCW para cada objeto COM, independientemente del número de referencias que existan en ese objeto. CLR mantiene un único contenedor RCW por proceso para cada objeto.  Si crea un contenedor RCW en un dominio de aplicación o apartamento y después pasa una referencia a otro dominio de aplicación o apartamento, se usará un proxy para el primer objeto.  Como se muestra en la siguiente ilustración, cualquier número de clientes administrados puede contener una referencia a los objetos COM que exponen las interfaces INew e INewer.  

En la imagen siguiente se muestra el proceso para obtener acceso a objetos COM a través del contenedor RCW:

 ![Proceso para obtener acceso a objetos COM a través del contenedor RCW.](./media/runtime-callable-wrapper/runtime-callable-wrapper.gif)  

 Usando los metadatos derivados de una biblioteca de tipos, CLR crea el objeto COM al que se está llamando y un contenedor para dicho objeto. Cada contenedor RCW mantiene una memoria caché de punteros de interfaz en el objeto COM que contiene y libera su referencia en el objeto COM cuando el contenedor RCW ya no es necesario. CLR realiza la recolección de elementos no utilizados en el contenedor RCW.  
  
 Entre otras actividades, el contenedor RCW calcula referencias de datos entre el código administrado y no administrado, en nombre del objeto encapsulado. El contenedor RCW proporciona específicamente serialización para argumentos de métodos y valores devueltos de métodos cada vez que el cliente y el servidor tienen representaciones diferentes de los datos que se pasan entre ellos.  
  
 El contenedor estándar impone las reglas de cálculo de referencias integradas. Por ejemplo, cuando un cliente .NET pasa un tipo String como parte de un argumento a un objeto no administrado, el contenedor convierte la cadena en un tipo BSTR. Si el objeto COM devuelve una cadena BSTR a su llamador administrado, el llamador recibe una cadena. Tanto el cliente como el servidor envían y reciben datos que les resultan familiares. Otros tipos no requieren conversión. Por ejemplo, un contenedor estándar pasará siempre un entero de 4 bytes entre el código administrado y no administrado sin convertir el tipo.  
  
## <a name="marshaling-selected-interfaces"></a>Serialización de interfaces seleccionadas  
 El objetivo principal del [contenedor RCW](runtime-callable-wrapper.md) es ocultar las diferencias entre los modelos de programación administrada y no administrada. Para crear una transición fluida, el contenedor RCW consume interfaces COM seleccionadas sin exponerlas al cliente .NET, tal y como se muestra en la siguiente ilustración.

 En la imagen siguiente se muestran las interfaces COM y el contenedor RCW:
  
 ![Captura de pantalla del contenedor RCW con interfaces.](./media/runtime-callable-wrapper/runtime-callable-wrapper-interfaces.gif)  
  
 Cuando se crea como un objeto de enlace en tiempo de compilación, el contenedor RCW es un tipo específico. Implementa las interfaces que el objeto COM implementa, y expone los métodos, las propiedades y los eventos de las interfaces del objeto. En la ilustración, el contenedor RCW expone la interfaz INew pero consume las interfaces **IUnknown** e **IDispatch**. Además, el contenedor RCW expone todos los miembros de la interfaz INew al cliente .NET.  
  
 El contenedor RCW consume las interfaces enumeradas en la siguiente tabla, expuestas por el objeto que encapsula.  
  
|Interfaz|Description|  
|---------------|-----------------|  
|**IDispatch**|Para el enlace en tiempo de ejecución a objetos COM mediante reflexión.|  
|**IErrorInfo**|Proporciona una descripción textual del error, su origen, un archivo de ayuda, contexto de ayuda y el GUID de la interfaz que definió el error (siempre **GUID_NULL** para las clases. NET).|  
|**IProvideClassInfo**|Si el objeto COM que se está encapsulando implementa **IProvideClassInfo**, el contenedor RCW extrae la información de tipos de esta interfaz para proporcionar una mejor identidad de tipos.|  
|**IUnknown**|Para la identidad de objetos, la conversión de tipos y la administración de la duración:<br /><br /> -   Identidad de objetos<br />     El tiempo de ejecución distingue los objetos COM comparando el valor de la interfaz **IUnknown** de cada objeto.<br />-   Coerción de tipos<br />     El contenedor RCW reconoce la detección dinámica de tipos que realiza el método **QueryInterface**.<br />-   Administración de la duración<br />     Con el método **QueryInterface**, el contenedor RCW obtiene y mantiene una referencia a un objeto no administrado hasta que CLR realiza la recolección de elementos no utilizados en el contenedor, lo que libera el objeto no administrado.|  
  
 Opcionalmente, el contenedor RCW consume las interfaces enumeradas en la siguiente tabla, expuestas por el objeto que encapsula.  
  
|Interfaz|Description|  
|---------------|-----------------|  
|**IConnectionPoint** e **IConnectionPointContainer**|El contenedor RCW convierte los objetos que exponen el estilo de evento de punto de conexión en eventos basados en delegado.|  
|**IDispatchEx** (solo .NET Framework) |Si la clase implementa **IDispatchEx**, el contenedor RCW implementa **IExpando**. La interfaz **IDispatchEx** es una extensión de la interfaz **IDispatch** que, a diferencia de **IDispatch**, permite enumerar, agregar, eliminar y llamar a miembros con distinción de mayúsculas y minúsculas.|  
|**IEnumVARIANT**|Permite tratar como colecciones a los tipos COM que admiten enumeraciones.|  
  
## <a name="see-also"></a>Vea también

- [Contenedores COM](com-wrappers.md)
- [Contenedor CCW (COM callable wrapper)](com-callable-wrapper.md)
- [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Importar una biblioteca de tipos como un ensamblado](../../framework/interop/importing-a-type-library-as-an-assembly.md)
