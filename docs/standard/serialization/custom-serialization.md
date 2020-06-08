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
# <a name="custom-serialization"></a><span data-ttu-id="b73de-104">Serialización personalizada</span><span class="sxs-lookup"><span data-stu-id="b73de-104">Custom serialization</span></span>
<span data-ttu-id="b73de-105">La serialización personalizada es el proceso de controlar la serialización y deserialización de un tipo.</span><span class="sxs-lookup"><span data-stu-id="b73de-105">Custom serialization is the process of controlling the serialization and deserialization of a type.</span></span> <span data-ttu-id="b73de-106">Controlando la serialización, es posible asegurarse compatibilidad de la serialización, que es la capacidad para serializar y deserializar entre las versiones de un tipo sin interrumpir la función básica del tipo.</span><span class="sxs-lookup"><span data-stu-id="b73de-106">By controlling serialization, it's possible to ensure serialization compatibility, which is the ability to serialize and deserialize between versions of a type without breaking the core functionality of the type.</span></span> <span data-ttu-id="b73de-107">En la primera versión de un tipo, puede haber por ejemplo, solo dos campos.</span><span class="sxs-lookup"><span data-stu-id="b73de-107">For example, in the first version of a type, there may be only two fields.</span></span> <span data-ttu-id="b73de-108">En la versión siguiente de un tipo, se agregan varios campos más.</span><span class="sxs-lookup"><span data-stu-id="b73de-108">In the next version of a type, several more fields are added.</span></span> <span data-ttu-id="b73de-109">Todavía la segunda versión de una aplicación debe poder serializar y deserializar ambos tipos.</span><span class="sxs-lookup"><span data-stu-id="b73de-109">Yet the second version of an application must be able to serialize and deserialize both types.</span></span> <span data-ttu-id="b73de-110">En las secciones siguientes se describe cómo controlar la serialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-110">The following sections describe how to control serialization.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> <span data-ttu-id="b73de-111">En versiones previas a .NET Framework 4.0, la serialización de datos de usuario personalizados de un ensamblado de confianza parcial se realizaba mediante el método GetObjectData.</span><span class="sxs-lookup"><span data-stu-id="b73de-111">In versions previous to .NET Framework 4.0, serialization of custom user data in a partially trusted assembly was accomplished using the GetObjectData.</span></span> <span data-ttu-id="b73de-112">A partir de la versión 4.0, ese método se marca con el atributo de la clase <xref:System.Security.SecurityCriticalAttribute> que impide la ejecución en ensamblados de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="b73de-112">Starting with version 4.0, that method is marked with the <xref:System.Security.SecurityCriticalAttribute> attribute which prevents execution in partially trusted assemblies.</span></span> <span data-ttu-id="b73de-113">Para solucionarlo, implemente la interfaz <xref:System.Runtime.Serialization.ISafeSerializationData>.</span><span class="sxs-lookup"><span data-stu-id="b73de-113">To work around this condition, implement the <xref:System.Runtime.Serialization.ISafeSerializationData> interface.</span></span>  
  
## <a name="running-custom-methods-during-and-after-serialization"></a><span data-ttu-id="b73de-114">Ejecutar los métodos personalizados durante y después de la serialización</span><span class="sxs-lookup"><span data-stu-id="b73de-114">Running custom methods during and after serialization</span></span>  
 <span data-ttu-id="b73de-115">El procedimiento recomendado y la manera más fácil (se introduce en la versión 2.0 de .NET Framework) es aplicar los atributos siguientes a los métodos que se utilizan para corregir los datos durante y después de la serialización:</span><span class="sxs-lookup"><span data-stu-id="b73de-115">The best practice and easiest way (introduced in version 2.0 of the .NET Framework) is to apply the following attributes to methods that are used to correct data during and after serialization:</span></span>  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 <span data-ttu-id="b73de-116">Estos atributos permiten al tipo participar en cualquiera de las cuatro fases de los procesos de deserialización y serialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-116">These attributes allow the type to participate in any one of, or all four of the phases, of the serialization and deserialization processes.</span></span> <span data-ttu-id="b73de-117">Los atributos especifican los métodos del tipo que se debe invocar durante cada fase.</span><span class="sxs-lookup"><span data-stu-id="b73de-117">The attributes specify the methods of the type that should be invoked during each phase.</span></span> <span data-ttu-id="b73de-118">Los métodos no tienen acceso a la secuencia de la serialización pero en su lugar le permiten modificar el objeto antes de y después de la serialización o antes de y después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-118">The methods do not access the serialization stream but instead allow you to alter the object before and after serialization, or before and after deserialization.</span></span> <span data-ttu-id="b73de-119">Los atributos se pueden aplicar en todos los niveles de la jerarquía de herencia de tipo y se llama a cada método en la jerarquía desde la base a los más derivados.</span><span class="sxs-lookup"><span data-stu-id="b73de-119">The attributes can be applied at all levels of the type inheritance hierarchy, and each method is called in the hierarchy from the base to the most derived.</span></span> <span data-ttu-id="b73de-120">Este mecanismo evita la complejidad y cualquier problema resultante de implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> proporcionando la responsabilidad por la serialización y deserialización a la implementación más derivada.</span><span class="sxs-lookup"><span data-stu-id="b73de-120">This mechanism avoids the complexity and any resulting issues of implementing the <xref:System.Runtime.Serialization.ISerializable> interface by giving the responsibility for serialization and deserialization to the most derived implementation.</span></span> <span data-ttu-id="b73de-121">Además, este mecanismo permite a los formateadores omitir la población de campos y recuperación de la secuencia de la serialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-121">Additionally, this mechanism allows the formatters to ignore the population of fields and retrieval from the serialization stream.</span></span> <span data-ttu-id="b73de-122">Para obtener los detalles y ejemplos de controlar serialización y deserialización, haga clic en cualquiera de los vínculos anteriores.</span><span class="sxs-lookup"><span data-stu-id="b73de-122">For details and examples of controlling serialization and deserialization, click any of the previous links.</span></span>  
  
 <span data-ttu-id="b73de-123">Además, al agregar un nuevo campo a un tipo serializable existente, aplique el atributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> al campo.</span><span class="sxs-lookup"><span data-stu-id="b73de-123">In addition, when adding a new field to an existing serializable type, apply the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to the field.</span></span> <span data-ttu-id="b73de-124"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> omite la ausencia del campo cuando se procesa una secuencia que falta en el nuevo campo.</span><span class="sxs-lookup"><span data-stu-id="b73de-124">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignores the absence of the field when a stream that is missing the new field is processed.</span></span>  
  
## <a name="implementing-the-iserializable-interface"></a><span data-ttu-id="b73de-125">Implementar la interfaz ISerializable</span><span class="sxs-lookup"><span data-stu-id="b73de-125">Implementing the ISerializable interface</span></span>  
 <span data-ttu-id="b73de-126">La otra manera de controlar la serialización se logra implementando la interfaz <xref:System.Runtime.Serialization.ISerializable> en un objeto.</span><span class="sxs-lookup"><span data-stu-id="b73de-126">The other way to control serialization is achieved by implementing the <xref:System.Runtime.Serialization.ISerializable> interface on an object.</span></span> <span data-ttu-id="b73de-127">Tenga en cuenta, sin embargo, que el método en la sección anterior reemplaza este método para controlar la serialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-127">Note, however, that the method in the previous section supersedes this method to control serialization.</span></span>  
  
 <span data-ttu-id="b73de-128">Además, no debe usar la serialización predeterminada en una clase que se marca con el atributo [Serializable](xref:System.SerializableAttribute) y tiene declaración o seguridad imperativa en el nivel de clase o en sus constructores.</span><span class="sxs-lookup"><span data-stu-id="b73de-128">In addition, you should not use default serialization on a class that is marked with the [Serializable](xref:System.SerializableAttribute) attribute and has declarative or imperative security at the class level or on its constructors.</span></span> <span data-ttu-id="b73de-129">En su lugar, estas clases siempre deben implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="b73de-129">Instead, these classes should always implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 <span data-ttu-id="b73de-130">Implementar <xref:System.Runtime.Serialization.ISerializable>, implica implementar el método `GetObjectData` y un constructor especial que se usa cuando se deserializa el objeto.</span><span class="sxs-lookup"><span data-stu-id="b73de-130">Implementing <xref:System.Runtime.Serialization.ISerializable> involves implementing the `GetObjectData` method and a special constructor that is used when the object is deserialized.</span></span> <span data-ttu-id="b73de-131">El código de ejemplo siguiente muestra cómo implementar <xref:System.Runtime.Serialization.ISerializable> en la clase `MyObject` de una sección anterior.</span><span class="sxs-lookup"><span data-stu-id="b73de-131">The following sample code shows how to implement <xref:System.Runtime.Serialization.ISerializable> on the `MyObject` class from a previous section.</span></span>  
  
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
  
 <span data-ttu-id="b73de-132">Cuando se llama a **GetObjectData** durante la serialización, es responsable de rellenar el elemento <xref:System.Runtime.Serialization.SerializationInfo> proporcionado por la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="b73de-132">When **GetObjectData** is called during serialization, you are responsible for populating the <xref:System.Runtime.Serialization.SerializationInfo> provided with the method call.</span></span> <span data-ttu-id="b73de-133">Agregue las variables que se van a serializar como nombre y pares de valor.</span><span class="sxs-lookup"><span data-stu-id="b73de-133">Add the variables to be serialized as name and value pairs.</span></span> <span data-ttu-id="b73de-134">Cualquier texto se puede utilizar como nombre.</span><span class="sxs-lookup"><span data-stu-id="b73de-134">Any text can be used as the name.</span></span> <span data-ttu-id="b73de-135">Tiene la libertad para decidir qué variables miembro se agregan a <xref:System.Runtime.Serialization.SerializationInfo>, con tal de que los datos suficientes se serialicen para restaurar el objeto durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-135">You have the freedom to decide which member variables are added to the <xref:System.Runtime.Serialization.SerializationInfo>, provided that sufficient data is serialized to restore the object during deserialization.</span></span> <span data-ttu-id="b73de-136">Las clases derivadas deben llamar al método **GetObjectData** en el objeto base si el último implementa <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="b73de-136">Derived classes should call the **GetObjectData** method on the base object if the latter implements <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
 <span data-ttu-id="b73de-137">Observe que la serialización puede permitir a otro código ver o modificar datos de instancia de objeto que de lo contrario son inaccesibles.</span><span class="sxs-lookup"><span data-stu-id="b73de-137">Note that serialization can allow other code to see or modify object instance data that is otherwise inaccessible.</span></span> <span data-ttu-id="b73de-138">Por consiguiente, el código que realiza la serialización requiere [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificada.</span><span class="sxs-lookup"><span data-stu-id="b73de-138">Therefore, code that performs serialization requires the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="b73de-139">De acuerdo con la directiva predeterminada, no se concede este permiso al código descargado de Internet o de la intranet; únicamente el código del equipo local tiene garantizado este permiso.</span><span class="sxs-lookup"><span data-stu-id="b73de-139">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span> <span data-ttu-id="b73de-140">El método **GetObjectData** se debe proteger explícitamente o exigiendo el elemento [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificada o exigiendo otros permisos que específicamente ayudan a proteger los datos privados.</span><span class="sxs-lookup"><span data-stu-id="b73de-140">The **GetObjectData** method must be explicitly protected either by demanding the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified or by demanding other permissions that specifically help protect private data.</span></span>  
  
 <span data-ttu-id="b73de-141">Si un campo privado almacena información confidencial, debe exigir los permisos adecuados en **GetObjectData** para proteger los datos.</span><span class="sxs-lookup"><span data-stu-id="b73de-141">If a private field stores sensitive information, you should demand the appropriate permissions on **GetObjectData** to protect the data.</span></span> <span data-ttu-id="b73de-142">Recuerde que ese código al que se le ha concedido [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con la marca **SerializationFormatter** especificada puede ver y modificar los datos almacenados en campos privados.</span><span class="sxs-lookup"><span data-stu-id="b73de-142">Remember that code that has been granted [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the **SerializationFormatter** flag specified can view and modify the data stored in private fields.</span></span> <span data-ttu-id="b73de-143">Un autor de llamada malintencionado al que se le haya concedido este [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) puede ver datos como ubicaciones del directorio ocultas o permisos concedidos y usar los datos para aprovecharse de una vulnerabilidad de seguridad en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b73de-143">A malicious caller granted this [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) can view data such as hidden directory locations or granted permissions and use the data to exploit a security vulnerability on the computer.</span></span> <span data-ttu-id="b73de-144">Para obtener una lista completa de marcas de permiso de seguridad que puede especificar, vea [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).</span><span class="sxs-lookup"><span data-stu-id="b73de-144">For a complete list of the security permission flags you can specify, see the [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).</span></span>  
  
 <span data-ttu-id="b73de-145">Es importante enfatizar que cuando <xref:System.Runtime.Serialization.ISerializable> se agrega a una clase, se debe implementar **GetObjectData** y el constructor especial.</span><span class="sxs-lookup"><span data-stu-id="b73de-145">It's important to stress that when <xref:System.Runtime.Serialization.ISerializable> is added to a class you must implement both **GetObjectData** and the special constructor.</span></span> <span data-ttu-id="b73de-146">El compilador proporciona una advertencia si falta **GetObjectData**.</span><span class="sxs-lookup"><span data-stu-id="b73de-146">The compiler warns you if **GetObjectData** is missing.</span></span> <span data-ttu-id="b73de-147">Sin embargo, porque es imposible de exigir la implementación de un constructor, no se proporciona ninguna advertencia si el constructor está ausente, y se produce una excepción cuando se intenta deserializar una clase sin el constructor.</span><span class="sxs-lookup"><span data-stu-id="b73de-147">However, because it is impossible to enforce the implementation of a constructor, no warning is provided if the constructor is absent, and an exception is thrown when an attempt is made to deserialize a class without the constructor.</span></span>  
  
 <span data-ttu-id="b73de-148">El diseño actual se favoreció sobre un método <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> para ir alrededor de la seguridad potencial y los problemas controlando las versiones.</span><span class="sxs-lookup"><span data-stu-id="b73de-148">The current design was favored above a <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> method to get around potential security and versioning problems.</span></span> <span data-ttu-id="b73de-149">Por ejemplo, un método `SetObjectData` debe ser público si se define como parte de una interfaz; así los usuarios deben escribir el código para defenderse de llamar varias veces al método **SetObjectData**.</span><span class="sxs-lookup"><span data-stu-id="b73de-149">For example, a `SetObjectData` method must be public if it is defined as part of an interface; thus users must write code to defend against having the **SetObjectData** method called multiple times.</span></span> <span data-ttu-id="b73de-150">De lo contrario, una aplicación malintencionada que llama al método **SetObjectData** en un objeto en el proceso de ejecutar una operación puede producir los posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="b73de-150">Otherwise, a malicious application that calls the **SetObjectData** method on an object in the process of executing an operation can cause potential problems.</span></span>  
  
 <span data-ttu-id="b73de-151">Durante la deserialización, <xref:System.Runtime.Serialization.SerializationInfo> se pasa a la clase utilizando el constructor proporcionado para este propósito.</span><span class="sxs-lookup"><span data-stu-id="b73de-151">During deserialization, <xref:System.Runtime.Serialization.SerializationInfo> is passed to the class using the constructor provided for this purpose.</span></span> <span data-ttu-id="b73de-152">Se omite cualquier restricción de visibilidad colocada en el constructor cuando se deserializa el objeto; así que puede marcar la clase como pública, protegida, interna o privada.</span><span class="sxs-lookup"><span data-stu-id="b73de-152">Any visibility constraints placed on the constructor are ignored when the object is deserialized; so you can mark the class as public, protected, internal, or private.</span></span> <span data-ttu-id="b73de-153">Sin embargo, es un procedimiento recomendado para proteger al constructor a menos que se selle la clase, en cuyo caso el constructor se debe marcar privado.</span><span class="sxs-lookup"><span data-stu-id="b73de-153">However, it is a best practice to make the constructor protected unless the class is sealed, in which case the constructor should be marked private.</span></span> <span data-ttu-id="b73de-154">El constructor también debe realizar la validación de entrada en profundidad.</span><span class="sxs-lookup"><span data-stu-id="b73de-154">The constructor should also perform thorough input validation.</span></span> <span data-ttu-id="b73de-155">Para evitar el mal uso por código dañino, el constructor debe exigir las mismas comprobaciones de seguridad y permisos exigidos para obtener una instancia de la clase utilizando cualquier otro constructor.</span><span class="sxs-lookup"><span data-stu-id="b73de-155">To avoid misuse by malicious code, the constructor should enforce the same security checks and permissions required to obtain an instance of the class using any other constructor.</span></span> <span data-ttu-id="b73de-156">Si no sigue esta recomendación, el código malintencionado puede preserializar un objeto, obtener el control con el [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con el marcador <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> especificado y deserializar el objeto en un equipo cliente que omite cualquier seguridad que se habría aplicado durante la construcción de la instancia estándar usando un constructor público.</span><span class="sxs-lookup"><span data-stu-id="b73de-156">If you do not follow this recommendation, malicious code can preserialize an object, obtain control with the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified and deserialize the object on a client computer bypassing any security that would have been applied during standard instance construction using a public constructor.</span></span>  
  
 <span data-ttu-id="b73de-157">Para restaurar el estado del objeto, simplemente recupere los valores de las variables de <xref:System.Runtime.Serialization.SerializationInfo> utilizando los nombres utilizó durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-157">To restore the state of the object, simply retrieve the values of the variables from <xref:System.Runtime.Serialization.SerializationInfo> using the names used during serialization.</span></span> <span data-ttu-id="b73de-158">Si la clase base implementa <xref:System.Runtime.Serialization.ISerializable>, se debe llamar al constructor base para permitir al objeto base restaurar sus variables.</span><span class="sxs-lookup"><span data-stu-id="b73de-158">If the base class implements <xref:System.Runtime.Serialization.ISerializable>, the base constructor should be called to allow the base object to restore its variables.</span></span>  
  
 <span data-ttu-id="b73de-159">Al derivar una nueva clase de uno que implementa <xref:System.Runtime.Serialization.ISerializable>, la clase derivada debe implementar ambos, el constructor y el método **GetObjectData** si tiene variables que necesitan serializarse.</span><span class="sxs-lookup"><span data-stu-id="b73de-159">When you derive a new class from one that implements <xref:System.Runtime.Serialization.ISerializable>, the derived class must implement both the constructor as well as the **GetObjectData** method if it has variables that need to be serialized.</span></span> <span data-ttu-id="b73de-160">El ejemplo de código siguiente muestra cómo esto se hace utilizando la clase `MyObject` mostrada previamente.</span><span class="sxs-lookup"><span data-stu-id="b73de-160">The following code example shows how this is done using the `MyObject` class shown previously.</span></span>  
  
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
  
 <span data-ttu-id="b73de-161">No se olvide de llamar a la clase base en el constructor de deserialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-161">Don't forget to call the base class in the deserialization constructor.</span></span> <span data-ttu-id="b73de-162">Si no se hace esto, nunca se llama al constructor en la clase base y el objeto no se construye totalmente después de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="b73de-162">If this isn't done, the constructor on the base class is never called, and the object is not fully constructed after deserialization.</span></span>  
  
 <span data-ttu-id="b73de-163">Los objetos se reconstruyen al revés; y llamar a los métodos durante la deserialización puede tener efectos secundarios indeseables, porque los métodos llamados podrían hacer referencia a las referencias que no se han deserializado cuando se realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="b73de-163">Objects are reconstructed from the inside out; and calling methods during deserialization can have undesirable side effects, because the methods called might refer to object references that have not been deserialized by the time the call is made.</span></span> <span data-ttu-id="b73de-164">Si la clase deserializada implementa <xref:System.Runtime.Serialization.IDeserializationCallback>, se llama al método <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> automáticamente cuando se ha deserializado el gráfico de objetos completo.</span><span class="sxs-lookup"><span data-stu-id="b73de-164">If the class being deserialized implements the <xref:System.Runtime.Serialization.IDeserializationCallback>, the <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> method is automatically called when the entire object graph has been deserialized.</span></span> <span data-ttu-id="b73de-165">Se han restaurado todos los objetos secundarios hechos referencia totalmente en este punto.</span><span class="sxs-lookup"><span data-stu-id="b73de-165">At this point, all the child objects referenced have been fully restored.</span></span> <span data-ttu-id="b73de-166">Una tabla hash es un ejemplo típico de una clase que es difícil de deserializar sin utilizar el agente de escucha de evento.</span><span class="sxs-lookup"><span data-stu-id="b73de-166">A hash table is a typical example of a class that is difficult to deserialize without using the event listener.</span></span> <span data-ttu-id="b73de-167">Es fácil de recuperar los pares de valor y clave durante la deserialización, pero volver a agregar estos objetos a la tabla hash puede producir los problemas, porque no hay ninguna garantía de que se hayan deserializado las clases que derivaron de la tabla hash.</span><span class="sxs-lookup"><span data-stu-id="b73de-167">It is easy to retrieve the key and value pairs during deserialization, but adding these objects back to the hash table can cause problems, because there is no guarantee that classes that derived from the hash table have been deserialized.</span></span> <span data-ttu-id="b73de-168">Llamar a los métodos en una tabla hash en esta copia intermedia no es, por consiguiente, aconsejable.</span><span class="sxs-lookup"><span data-stu-id="b73de-168">Calling methods on a hash table at this stage is therefore not advisable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73de-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="b73de-169">See also</span></span>

- [<span data-ttu-id="b73de-170">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="b73de-170">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="b73de-171">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="b73de-171">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="b73de-172">Seguridad y serialización</span><span class="sxs-lookup"><span data-stu-id="b73de-172">Security and Serialization</span></span>](../../framework/misc/security-and-serialization.md)
