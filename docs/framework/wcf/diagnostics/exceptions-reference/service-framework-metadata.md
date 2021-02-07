---
description: 'Más información sobre: metadatos del marco de trabajo de servicio'
title: Metadatos del marco de trabajo del servicio
ms.date: 03/30/2017
ms.assetid: 76afc73a-0770-4084-93f3-6701a757911e
ms.openlocfilehash: d5443627e3bb4f15e0d7bc154e5735c7ef639320
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686211"
---
# <a name="service-framework-metadata"></a>Metadatos del marco de trabajo del servicio

En este tema se enumeran las excepciones generadas por Service Framework Metadata.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|AsyncEndCalledOnWrongChannel|Se llamó a un End asincrónico en el canal equivocado.|  
|AsyncEndCalledWithAnIAsyncResult|Se llamó a un End asincrónico con un IAsyncResult desde un método Begin diferente.|  
|AttemptedToGetContractTypeForButThatTypeIs1|Se intentó obtener el tipo de contrato para el especificado. El tipo no es ServiceContract y no hereda ServiceContract.|  
|CannotHaveTwoOperationsWithTheSameName3|No se pueden tener dos operaciones en el mismo contrato con el mismo nombre. Los métodos especificados en el tipo especificado infringen esta regla. Cambie el nombre de una de las operaciones cambiando el nombre del método o utilizando la propiedad Name de OperationContractAttribute.|  
|CannotInheritTwoOperationsWithTheSameName3|No puede heredar dos operaciones diferentes con el mismo nombre. La operación especificada de los contratos especificados infringe esta regla. Cambie el nombre de una de las operaciones cambiando el nombre del método o utilizando la propiedad Name de OperationContractAttribute.|  
|CantCreateChannelWithManualAddressing|No puede crear un canal para un contrato que requiera una solicitud/respuesta y un enlace que requiera un direccionamiento manual pero solo admite la comunicación dúplex.|  
|DuplicateBehavior1|El valor no se puede agregar a la colección. La colección ya contiene un elemento del mismo tipo especificado. Esta colección solo admite una instancia de cada tipo.|  
|InAContractInheritanceHierarchyIfParentHasCallbackChildMustToo|Dado que el contrato de servicios base especificado tiene un contrato de devolución de llamada especificado, el contrato de servicios derivado especificado también debe especificar el tipo especificado o un tipo derivado como su contrato de devolución de llamada.|  
|InvalidAsyncBeginMethodSignatureForMethod2|Firma del método asincrónico Begin no válida para el método especificado en el tipo ServiceContract especificado. Su método Begin debe tomar una AsyncCallback y un objeto como los últimos dos argumentos y devolver un IAsyncResult.|  
|InvalidAsyncEndMethodSignatureForMethod2|Firma del método asincrónico End no válida para el método especificado en el tipo ServiceContract especificado. Su método End debe tomar IAsyncResult como el último argumento.|  
|MessagePropertiesArraySize0|La matriz que se pasó no tiene suficiente espacio para contener todas las propiedades contenidas por esta colección.|  
|OneWayAndFaultsIncompatible2|El método especificado en el tipo especificado se marca como IsOneWay=true y declara uno o más FaultContractAttributes. Los métodos unidireccionales no pueden declarar FaultContractAttributes. Cambie IsOneWay a false o elimine los FaultContractAttributes.|  
|UnsupportedWSDLOnlyOneMessage|Lenguaje de descripción de servicios Web no admitido Solo una parte del mensaje se admite para los mensajes de error. Este mensaje de error hace referencia a más de una parte del mensaje. Si tiene acceso de edición al archivo del lenguaje de descripción de servicios Web, puede corregir el problema eliminando las partes de mensaje adicionales de modo que el mensaje de error solo haga referencia a una parte.|  
|UnsupportedWSDLTheFault|Lenguaje de descripción de servicios Web no admitido La parte del mensaje de error debe hacer referencia a un elemento. Este mensaje de error no hace referencia a un elemento. Si tiene acceso de edición al documento del lenguaje de descripción de servicios Web, puede corregir el problema haciendo referencia a un elemento de esquema utilizando el atributo “element”.|  
|WsdlImportErrorDependencyDetail|Se produjo un error al importar lo especificado del que depende el otro valor especificado. También se especifica el Xpath.|  
|XsdMissingRequiredAttribute1|Falta el atributo necesario especificado.|
