---
title: Serialización personalizada
description: La serialización personalizada es el control de la serialización y la deserialización de un tipo. El control de la serialización puede garantizar la compatibilidad de la serialización.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binary serialization, custom serialization
- custom serialization
- binary serialization, controlling
- OptionalFieldAttribute class, custom serialization
- ISerializable interface, custom serialization
- OnDeserializingAttribute class, custom serialization
- OnSerializedAttribute class, custom serialization
- serialization, custom serialization
- serialization, controlling
- OnDeserializedAttribute class, custom serialization
- OnSerializingAttribute class, custom serialization
ms.assetid: 12ed422d-5280-49b8-9b71-a2ed129c0384
ms.openlocfilehash: 1532c4eeb09e7110d0f369ec47f342256889e576
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289660"
---
# <a name="custom-serialization"></a>Serialización personalizada
La serialización personalizada es el proceso de controlar la serialización y deserialización de un tipo. Controlando la serialización, es posible asegurarse compatibilidad de la serialización, que es la capacidad para serializar y deserializar entre las versiones de un tipo sin interrumpir la función básica del tipo. En la primera versión de un tipo, puede haber por ejemplo, solo dos campos. En la versión siguiente de un tipo, se agregan varios campos más. Todavía la segunda versión de una aplicación debe poder serializar y deserializar ambos tipos. En las secciones siguientes se describe cómo controlar la serialización.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> En versiones previas a .NET Framework 4.0, la serialización de datos de usuario personalizados de un ensamblado de confianza parcial se realizaba mediante el método GetObjectData. A partir de la versión 4.0, ese método se marca con el atributo de la clase <xref:System.Security.SecurityCriticalAttribute> que impide la ejecución en ensamblados de confianza parcial. Para solucionarlo, implemente la interfaz <xref:System.Runtime.Serialization.ISafeSerializationData>.  
  
## <a name="running-custom-methods-during-and-after-serialization"></a>Ejecutar los métodos personalizados durante y después de la serialización  
 El procedimiento recomendado y la manera más fácil (se introduce en la versión 2.0 de .NET Framework) es aplicar los atributos siguientes a los métodos que se utilizan para corregir los datos durante y después de la serialización:  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 Estos atributos permiten al tipo participar en cualquiera de las cuatro fases de los procesos de deserialización y serialización. Los atributos especifican los métodos del tipo que se debe invocar durante cada fase. Los métodos no tienen acceso a la secuencia de la serialización pero en su lugar le permiten modificar el objeto antes de y después de la serialización o antes de y después de la deserialización. Los atributos se pueden aplicar en todos los niveles de la jerarquía de herencia de tipo y se llama a cada método en la jerarquía desde la base a los más derivados. Este mecanismo evita la complejidad y cualquier problema resultante de implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> proporcionando la responsabilidad por la serialización y deserialización a la implementación más derivada. Además, este mecanismo permite a los formateadores omitir la población de campos y recuperación de la secuencia de la serialización. Para obtener los detalles y ejemplos de controlar serialización y deserialización, haga clic en cualquiera de los vínculos anteriores.  
  
 Además, al agregar un nuevo campo a un tipo serializable existente, aplique el atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> al campo. <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> omite la ausencia del campo cuando se procesa una secuencia que falta en el nuevo campo.  
  
## <a name="implementing-the-iserializable-interface"></a>Implementar la interfaz ISerializable  
 La otra manera de controlar la serialización se logra implementando la interfaz <xref:System.Runtime.Serialization.ISerializable> en un objeto. Tenga en cuenta, sin embargo, que el método en la sección anterior reemplaza este método para controlar la serialización.  
  
 Además, no debe usar la serialización predeterminada en una clase que se marca con el atributo [Serializable](xref:System.SerializableAttribute) y tiene declaración o seguridad imperativa en el nivel de clase o en sus constructores. En su lugar, estas clases siempre deben implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
 Implementar <xref:System.Runtime.Serialization.ISerializable>, implica implementar el método `GetObjectData` y un constructor especial que se usa cuando se deserializa el objeto. El código de ejemplo siguiente muestra cómo implementar <xref:System.Runtime.Serialization.ISerializable> en la clase `MyObject` de una sección anterior.  
  
```csharp
[Serializable]
public class MyObject : ISerializable
{
    public int n1;
    public int n2;
    public String str;

    public MyObject()
    {
    }

    protected MyObject(SerializationInfo info, StreamingContext context)
    {
      n1 = info.GetInt32("i");
      n2 = info.GetInt32("j");
      str = info.GetString("k");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public virtual void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        info.AddValue("i", n1);
        info.AddValue("j", n2);
        info.AddValue("k", str);
    }
}
```

```vb
<Serializable()>  _
Public Class MyObject
    Implements ISerializable
    Public n1 As Integer
    Public n2 As Integer
    Public str As String

    Public Sub New()
    End Sub

    Protected Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        n1 = info.GetInt32("i")
        n2 = info.GetInt32("j")
        str = info.GetString("k")
    End Sub 'New

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overridable Sub GetObjectData(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        info.AddValue("i", n1)
        info.AddValue("j", n2)
        info.AddValue("k", str)
    End Sub
End Class
```  
  
 Cuando se llama a **GetObjectData** durante la serialización, es responsable de rellenar el elemento <xref:System.Runtime.Serialization.SerializationInfo> proporcionado por la llamada al método. Agregue las variables que se van a serializar como nombre y pares de valor. Cualquier texto se puede utilizar como nombre. Tiene la libertad para decidir qué variables miembro se agregan a <xref:System.Runtime.Serialization.SerializationInfo>, con tal de que los datos suficientes se serialicen para restaurar el objeto durante la deserialización. Las clases derivadas deben llamar al método **GetObjectData** en el objeto base si el último implementa <xref:System.Runtime.Serialization.ISerializable>.  
  
 Observe que la serialización puede permitir a otro código ver o modificar datos de instancia de objeto que de lo contrario son inaccesibles. Por consiguiente, el código que realiza la serialización requiere [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificada. De acuerdo con la directiva predeterminada, no se concede este permiso al código descargado de Internet o de la intranet; únicamente el código del equipo local tiene garantizado este permiso. El método **GetObjectData** se debe proteger explícitamente o exigiendo el elemento [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificada o exigiendo otros permisos que específicamente ayudan a proteger los datos privados.  
  
 Si un campo privado almacena información confidencial, debe exigir los permisos adecuados en **GetObjectData** para proteger los datos. Recuerde que ese código al que se le ha concedido [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca **SerializationFormatter** especificada puede ver y modificar los datos almacenados en campos privados. Un autor de llamada malintencionado al que se le haya concedido este [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) puede ver datos como ubicaciones del directorio ocultas o permisos concedidos y usar los datos para aprovecharse de una vulnerabilidad de seguridad en el equipo. Para obtener una lista completa de marcas de permiso de seguridad que puede especificar, vea [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).  
  
 Es importante enfatizar que cuando <xref:System.Runtime.Serialization.ISerializable> se agrega a una clase, se debe implementar **GetObjectData** y el constructor especial. El compilador proporciona una advertencia si falta **GetObjectData**. Sin embargo, porque es imposible de exigir la implementación de un constructor, no se proporciona ninguna advertencia si el constructor está ausente, y se produce una excepción cuando se intenta deserializar una clase sin el constructor.  
  
 El diseño actual se favoreció sobre un método <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> para ir alrededor de la seguridad potencial y los problemas controlando las versiones. Por ejemplo, un método `SetObjectData` debe ser público si se define como parte de una interfaz; así los usuarios deben escribir el código para defenderse de llamar varias veces al método **SetObjectData**. De lo contrario, una aplicación malintencionada que llama al método **SetObjectData** en un objeto en el proceso de ejecutar una operación puede producir los posibles problemas.  
  
 Durante la deserialización, <xref:System.Runtime.Serialization.SerializationInfo> se pasa a la clase utilizando el constructor proporcionado para este propósito. Se omite cualquier restricción de visibilidad colocada en el constructor cuando se deserializa el objeto; así que puede marcar la clase como pública, protegida, interna o privada. Sin embargo, es un procedimiento recomendado para proteger al constructor a menos que se selle la clase, en cuyo caso el constructor se debe marcar privado. El constructor también debe realizar la validación de entrada en profundidad. Para evitar el mal uso por código dañino, el constructor debe exigir las mismas comprobaciones de seguridad y permisos exigidos para obtener una instancia de la clase utilizando cualquier otro constructor. Si no sigue esta recomendación, el código malintencionado puede preserializar un objeto, obtener el control con el [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con el marcador <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificado y deserializar el objeto en un equipo cliente que omite cualquier seguridad que se habría aplicado durante la construcción de la instancia estándar usando un constructor público.  
  
 Para restaurar el estado del objeto, simplemente recupere los valores de las variables de <xref:System.Runtime.Serialization.SerializationInfo> utilizando los nombres utilizó durante la serialización. Si la clase base implementa <xref:System.Runtime.Serialization.ISerializable>, se debe llamar al constructor base para permitir al objeto base restaurar sus variables.  
  
 Al derivar una nueva clase de uno que implementa <xref:System.Runtime.Serialization.ISerializable>, la clase derivada debe implementar ambos, el constructor y el método **GetObjectData** si tiene variables que necesitan serializarse. El ejemplo de código siguiente muestra cómo esto se hace utilizando la clase `MyObject` mostrada previamente.  
  
```csharp
[Serializable]
public class ObjectTwo : MyObject
{
    public int num;

    public ObjectTwo()
      : base()
    {
    }

    protected ObjectTwo(SerializationInfo si, StreamingContext context)
      : base(si, context)
    {
        num = si.GetInt32("num");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public override void GetObjectData(SerializationInfo si, StreamingContext context)
    {
        base.GetObjectData(si,context);
        si.AddValue("num", num);
    }
}
```

```vb
<Serializable()>  _
Public Class ObjectTwo
    Inherits MyObject
    Public num As Integer

    Public Sub New()

    End Sub

    Protected Sub New(ByVal si As SerializationInfo, _
    ByVal context As StreamingContext)
        MyBase.New(si, context)
        num = si.GetInt32("num")
    End Sub

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overrides Sub GetObjectData(ByVal si As SerializationInfo, ByVal context As StreamingContext)
        MyBase.GetObjectData(si, context)
        si.AddValue("num", num)
    End Sub
End Class
```  
  
 No se olvide de llamar a la clase base en el constructor de deserialización. Si no se hace esto, nunca se llama al constructor en la clase base y el objeto no se construye totalmente después de la deserialización.  
  
 Los objetos se reconstruyen al revés; y llamar a los métodos durante la deserialización puede tener efectos secundarios indeseables, porque los métodos llamados podrían hacer referencia a las referencias que no se han deserializado cuando se realiza la llamada. Si la clase deserializada implementa <xref:System.Runtime.Serialization.IDeserializationCallback>, se llama al método <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> automáticamente cuando se ha deserializado el gráfico de objetos completo. Se han restaurado todos los objetos secundarios hechos referencia totalmente en este punto. Una tabla hash es un ejemplo típico de una clase que es difícil de deserializar sin utilizar el agente de escucha de evento. Es fácil de recuperar los pares de valor y clave durante la deserialización, pero volver a agregar estos objetos a la tabla hash puede producir los problemas, porque no hay ninguna garantía de que se hayan deserializado las clases que derivaron de la tabla hash. Llamar a los métodos en una tabla hash en esta copia intermedia no es, por consiguiente, aconsejable.  
  
## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Seguridad y serialización](../../framework/misc/security-and-serialization.md)
