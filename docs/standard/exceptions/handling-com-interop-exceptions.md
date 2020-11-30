---
title: Controlar excepciones de interoperabilidad COM
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
ms.openlocfilehash: 42efd1a5622bae7c476c92fb0864a6214c9bac9b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726189"
---
# <a name="handling-com-interop-exceptions"></a>Controlar excepciones de interoperabilidad COM

El código administrado y el código no administrado pueden trabajar juntos para controlar excepciones. Si un método produce una excepción en código administrado, Common Language Runtime puede pasar un HRESULT a un objeto COM. Si un método produce un error en código no administrado y devuelve un HRESULT de error, el tiempo de ejecución produce una excepción que el código administrado puede capturar.  
  
 El tiempo de ejecución asigna automáticamente el HRESULT de la interoperabilidad COM a excepciones más específicas. Por ejemplo, E_ACCESSDENIED se convierte en <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY se convierte en <xref:System.OutOfMemoryException>, y así sucesivamente.  
  
 Si el HRESULT es un resultado personalizado o es desconocido para el tiempo de ejecución, este pasa una <xref:System.Runtime.InteropServices.COMException> genérica al cliente. La propiedad **ErrorCode** de **COMException** contiene el valor HRESULT.  
  
## <a name="working-with-ierrorinfo"></a>Trabajar con IErrorInfo  

 Cuando se pasa un error desde COM al código administrado, el tiempo de ejecución rellena el objeto de excepción con la información del error. Los objetos COM que admiten IErrorInfo y devuelven HRESULTS proporcionan esta información a las excepciones de código administrado. Por ejemplo, el tiempo de ejecución asigna la descripción del error COM a la propiedad <xref:System.Exception.Message%2A> de la excepción. Si el valor HRESULT no proporciona ninguna información de error adicional, el tiempo de ejecución rellena muchas de las propiedades de la excepción con los valores predeterminados.  
  
 Si un método produce un error en código no administrado, se puede pasar una excepción a un segmento de código administrado. El tema [HRESULT y excepciones](../../framework/interop/how-to-map-hresults-and-exceptions.md) contiene una tabla que muestra cómo se asignan los HRESULTS a los objetos de excepción en tiempo de ejecución.  

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
