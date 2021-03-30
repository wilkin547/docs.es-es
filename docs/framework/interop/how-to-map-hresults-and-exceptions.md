---
title: Procedimiento para asignar resultados HRESULT y excepciones
description: Revise cómo asignar los valores HRESULT devueltos de los métodos COM a las excepciones producidas por los métodos de .NET. El tiempo de ejecución controla la transición entre COM y .NET.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- interoperation with unmanaged code, HRESULTs
- exceptions, HRESULTs
- interoperation with unmanaged code, exceptions
- HRESULTs
- COM interop, HRESULTs
- COM interop, exceptions
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
ms.openlocfilehash: 13798de1547428d54c10f83c41a5a402e2b3fb53
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872410"
---
# <a name="how-to-map-hresults-and-exceptions"></a>Procedimiento para asignar resultados HRESULT y excepciones

Los métodos COM informan de errores devolviendo valores HRESULT; los métodos de .NET informan de ellos iniciando excepciones. El tiempo de ejecución controla la transición entre los dos. Cada clase de excepción de .NET Framework se asigna a un valor HRESULT.

 Las clases de excepción definidas por el usuario pueden especificar el valor HRESULT que sea necesario. Estas clases de excepción pueden cambiar dinámicamente el valor HRESULT que se devuelve cuando se genera la excepción si se establece el campo `HResult` en el objeto de excepción. Se proporciona información adicional sobre la excepción al cliente a través de la interfaz `IErrorInfo`, que se implementa en el objeto .NET en el proceso no administrado.

 Si crea una clase que extienda `System.Exception`, debe establecer el campo HRESULT durante la construcción. En caso contrario, la clase base asigna el valor HRESULT. Puede asignar nuevas clases de excepción a un valor HRESULT existente proporcionando el valor en el constructor de la excepción.

 Tenga en cuenta que a veces el tiempo de ejecución omitirá un valor `HRESULT` en casos donde hay una `IErrorInfo` presente en el subproceso.  Este comportamiento puede aparecer en casos donde `HRESULT` y `IErrorInfo` no representan el mismo error.

### <a name="to-create-a-new-exception-class-and-map-it-to-an-hresult"></a>Para crear una nueva clase de excepción y asignarla a un valor HRESULT

1. Use el código siguiente para crear una nueva clase de excepción denominada `NoAccessException` y asignarla al valor HRESULT `E_ACCESSDENIED`.

    ```cpp
    Class NoAccessException : public ApplicationException
    {
        NoAccessException () {
        HResult = E_ACCESSDENIED;
    }
    }
    CMyClass::MethodThatThrows
    {
    throw new NoAccessException();
    }
    ```

 Es posible que encuentre un programa (en cualquier lenguaje de programación) que use tanto código administrado como no administrado al mismo tiempo. Por ejemplo, el serializador personalizado del ejemplo de código siguiente usa el método `Marshal.ThrowExceptionForHR(int HResult)` para iniciar una excepción con un valor HRESULT específico. El método busca el valor HRESULT y genera el tipo de excepción adecuado. Por ejemplo, el valor de HRESULT en el fragmento de código siguiente genera `ArgumentException`.

```cpp
CMyClass::MethodThatThrows
{
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);
}
```

 En la tabla siguiente se proporcionan las asignaciones comunes de HRESULT a su clase de excepción comparable en .NET. Los valores de HRESULT sin asignaciones explícitas se asignan a `COMException`. La asignación actualizada completa se puede encontrar en el [repositorio de dotnet/runtime](https://github.com/dotnet/runtime/blob/main/src/coreclr/vm/rexcep.h).

|HRESULT|Excepción de .NET|
|-------------|--------------------|
|`COR_E_APPLICATION`|`ApplicationException`|
|`COR_E_ARGUMENT` o `E_INVALIDARG`|`ArgumentException`|
|`COR_E_ARGUMENTOUTOFRANGE`|`ArgumentOutOfRangeException`|
|`COR_E_ARITHMETIC or ERROR_ARITHMETIC_OVERFLOW`|`ArithmeticException`|
|`COR_E_ARRAYTYPEMISMATCH`|`ArrayTypeMismatchException`|
|`COR_E_BADIMAGEFORMAT or ERROR_BAD_FORMAT`|`BadImageFormatException`|
|`COR_E_DIRECTORYNOTFOUND or ERROR_PATH_NOT_FOUND`|`DirectoryNotFoundException`|
|`COR_E_DIVIDEBYZERO`|`DivideByZeroException`|
|`COR_E_DUPLICATEWAITOBJECT`|`DuplicateWaitObjectException`|
|`COR_E_ENDOFSTREAM`|`EndOfStreamException`|
|`COR_E_ENTRYPOINTNOTFOUND`|`EntryPointNotFoundException`|
|`COR_E_EXCEPTION`|`Exception`|
|`COR_E_EXECUTIONENGINE`|`ExecutionEngineException`|
|`COR_E_FIELDACCESS`|`FieldAccessException`|
|`COR_E_FILENOTFOUND or ERROR_FILE_NOT_FOUND`|`FileNotFoundException`|
|`COR_E_FORMAT`|`FormatException`|
|`COR_E_INDEXOUTOFRANGE`|`IndexOutOfRangeException`|
|`COR_E_INVALIDCAST or E_NOINTERFACE`|`InvalidCastException`|
|`COR_E_INVALIDFILTERCRITERIA`|`InvalidFilterCriteriaException`|
|`COR_E_INVALIDOPERATION`|`InvalidOperationException`|
|`COR_E_IO`|`IOException`|
|`COR_E_MEMBERACCESS`|`AccessException`|
|`COR_E_METHODACCESS`|`MethodAccessException`|
|`COR_E_MISSINGFIELD`|`MissingFieldException`|
|`COR_E_MISSINGMANIFESTRESOURCE`|`MissingManifestResourceException`|
|`COR_E_MISSINGMEMBER`|`MissingMemberException`|
|`COR_E_MISSINGMETHOD`|`MissingMethodException`|
|`COR_E_NOTFINITENUMBER`|`NotFiniteNumberException`|
|`E_NOTIMPL`|`NotImplementedException`|
|`COR_E_NOTSUPPORTED`|`NotSupportedException`|
|`COR_E_NULLREFERENCE orE_POINTER`|`NullReferenceException`|
|`COR_E_OUTOFMEMORY or`<br /><br /> `E_OUTOFMEMORY`|`OutOfMemoryException`|
|`COR_E_OVERFLOW`|`OverflowException`|
|`COR_E_PATHTOOLONG or ERROR_FILENAME_EXCED_RANGE`|`PathTooLongException`|
|`COR_E_RANK`|`RankException`|
|`COR_E_REFLECTIONTYPELOAD`|`ReflectionTypeLoadException`|
|`COR_E_SECURITY`|`SecurityException`|
|`COR_E_SERIALIZATION`|`SerializationException`|
|`COR_E_STACKOVERFLOW orERROR_STACK_OVERFLOW`|`StackOverflowException`|
|`COR_E_SYNCHRONIZATIONLOCK`|`SynchronizationLockException`|
|`COR_E_SYSTEM`|`SystemException`|
|`COR_E_TARGET`|`TargetException`|
|`COR_E_TARGETINVOCATION`|`TargetInvocationException`|
|`COR_E_TARGETPARAMCOUNT`|`TargetParameterCountException`|
|`COR_E_THREADINTERRUPTED`|`ThreadInterruptedException`|
|`COR_E_THREADSTATE`|`ThreadStateException`|
|`COR_E_TYPELOAD`|`TypeLoadException`|
|`COR_E_TYPEINITIALIZATION`|`TypeInitializationException`|
|`COR_E_VERIFICATION`|`VerificationException`|

 Para recuperar información de error ampliada, el cliente administrado debe examinar los campos del objeto de excepción que se generó. Para que el objeto de excepción proporcione información útil sobre un error, el objeto COM debe implementar la interfaz `IErrorInfo`. El runtime usa la información proporcionada por `IErrorInfo` para inicializar el objeto de excepción.

 Si el objeto COM no es compatible con `IErrorInfo`, el tiempo de ejecución inicializa un objeto de excepción con los valores predeterminados. En la tabla siguiente se enumeran todos los campos asociados con un objeto de excepción y se identifica el origen de información de forma predeterminada cuando el objeto COM admite `IErrorInfo`.

 Tenga en cuenta que a veces el tiempo de ejecución omitirá un valor `HRESULT` en casos donde hay una `IErrorInfo` presente en el subproceso.  Este comportamiento puede aparecer en casos donde `HRESULT` y `IErrorInfo` no representan el mismo error.

|Campo de excepción|Origen de información de COM|
|---------------------|------------------------------------|
|`ErrorCode`|Valor HRESULT devuelto de la llamada.|
|`HelpLink`|Si `IErrorInfo->HelpContext` es distinto de cero, la cadena se forma concatenando `IErrorInfo->GetHelpFile` y "#" e `IErrorInfo->GetHelpContext`. En caso contrario, se devuelve la cadena desde `IErrorInfo->GetHelpFile`.|
|`InnerException`|Siempre una referencia nula (`Nothing` en Visual Basic).|
|`Message`|Cadena devuelta desde `IErrorInfo->GetDescription`.|
|`Source`|Cadena devuelta desde `IErrorInfo->GetSource`.|
|`StackTrace`|Seguimiento de la pila.|
|`TargetSite`|El nombre del método que devolvió el valor HRESULT con error.|

 Los campos de excepción, como `Message`, `Source` y `StackTrace` no están disponibles para la excepción `StackOverflowException`.

## <a name="see-also"></a>Vea también

- [Interoperabilidad COM avanzada](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Excepciones](../../standard/exceptions/index.md)
