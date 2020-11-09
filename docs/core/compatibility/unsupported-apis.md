---
title: API no admitidas en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga información sobre qué API de .NET siempre inician una excepción en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: 51d73557a48910d9cb1c4d3cdced34dfe4d849d8
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329786"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="281de-103">API que siempre inician excepciones en .NET Core y .NET 5+</span><span class="sxs-lookup"><span data-stu-id="281de-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="281de-104">Las API siguientes siempre iniciarán una excepción <xref:System.PlatformNotSupportedException> en .NET 5.0 y versiones posteriores (incluidas todas las versiones de .NET Core) en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="281de-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="281de-105">En este artículo, las API afectadas se organizan por espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="281de-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="281de-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="281de-106">This article is a work-in-progress.</span></span> <span data-ttu-id="281de-107">No es una lista completa de las API que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="281de-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="281de-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="281de-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="281de-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="281de-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="281de-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="281de-110">System</span></span>

| <span data-ttu-id="281de-111">Member</span><span class="sxs-lookup"><span data-stu-id="281de-111">Member</span></span> | <span data-ttu-id="281de-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-113">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="281de-114">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="281de-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="281de-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-117">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="281de-118">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="281de-119">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="281de-120">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-121">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="281de-122">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="281de-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="281de-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="281de-124">Member</span><span class="sxs-lookup"><span data-stu-id="281de-124">Member</span></span> | <span data-ttu-id="281de-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-126">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-127">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-128">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="281de-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="281de-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="281de-130">Member</span><span class="sxs-lookup"><span data-stu-id="281de-130">Member</span></span> | <span data-ttu-id="281de-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-132">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-133">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="281de-134">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="281de-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="281de-135">System.Configuration</span></span>

| <span data-ttu-id="281de-136">Member</span><span class="sxs-lookup"><span data-stu-id="281de-136">Member</span></span> | <span data-ttu-id="281de-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="281de-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="281de-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="281de-139">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="281de-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="281de-140">System.Console</span></span>

| <span data-ttu-id="281de-141">Member</span><span class="sxs-lookup"><span data-stu-id="281de-141">Member</span></span> | <span data-ttu-id="281de-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="281de-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-143">Linux and macOS</span></span> |
| <span data-ttu-id="281de-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-145">Linux and macOS</span></span> |
| <span data-ttu-id="281de-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-147">Linux and macOS</span></span> |
| <span data-ttu-id="281de-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-149">Linux and macOS</span></span> |
| <span data-ttu-id="281de-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="281de-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="281de-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-154">Linux and macOS</span></span> |
| <span data-ttu-id="281de-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="281de-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="281de-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-156">Linux and macOS</span></span> |
| <span data-ttu-id="281de-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-158">Linux and macOS</span></span> |
| <span data-ttu-id="281de-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-160">Linux and macOS</span></span> |
| <span data-ttu-id="281de-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-162">Linux and macOS</span></span> |
| <span data-ttu-id="281de-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="281de-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="281de-165">System.Data.Common</span></span>

| <span data-ttu-id="281de-166">Member</span><span class="sxs-lookup"><span data-stu-id="281de-166">Member</span></span> | <span data-ttu-id="281de-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="281de-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="281de-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="281de-169">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="281de-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="281de-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="281de-171">Member</span><span class="sxs-lookup"><span data-stu-id="281de-171">Member</span></span> | <span data-ttu-id="281de-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="281de-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-174">Linux</span><span class="sxs-lookup"><span data-stu-id="281de-174">Linux</span></span> |
| <span data-ttu-id="281de-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-176">Linux</span><span class="sxs-lookup"><span data-stu-id="281de-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="281de-177">macOS</span><span class="sxs-lookup"><span data-stu-id="281de-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="281de-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="281de-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="281de-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="281de-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="281de-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-183">Linux and macOS</span></span> |
| <span data-ttu-id="281de-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-185">Linux and macOS</span></span> |
| <span data-ttu-id="281de-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="281de-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="281de-187">macOS</span><span class="sxs-lookup"><span data-stu-id="281de-187">macOS</span></span> |
| <span data-ttu-id="281de-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="281de-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="281de-190">System.IO</span></span>

| <span data-ttu-id="281de-191">Member</span><span class="sxs-lookup"><span data-stu-id="281de-191">Member</span></span> | <span data-ttu-id="281de-192">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-193">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-194">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="281de-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="281de-195">System.IO.Pipes</span></span>

| <span data-ttu-id="281de-196">Member</span><span class="sxs-lookup"><span data-stu-id="281de-196">Member</span></span> | <span data-ttu-id="281de-197">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="281de-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="281de-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="281de-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="281de-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-201">Linux and macOS</span></span> |
| <span data-ttu-id="281de-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="281de-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="281de-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="281de-205">System.Media</span></span>

| <span data-ttu-id="281de-206">Member</span><span class="sxs-lookup"><span data-stu-id="281de-206">Member</span></span> | <span data-ttu-id="281de-207">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-208">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="281de-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="281de-209">System.Net</span></span>

| <span data-ttu-id="281de-210">Member</span><span class="sxs-lookup"><span data-stu-id="281de-210">Member</span></span> | <span data-ttu-id="281de-211">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="281de-212">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="281de-213">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-214">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-215">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-216">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-217">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-218">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-219">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-220">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-221">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-222">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="281de-223">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-224">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-225">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-226">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-227">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-228">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="281de-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="281de-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="281de-230">Member</span><span class="sxs-lookup"><span data-stu-id="281de-230">Member</span></span> | <span data-ttu-id="281de-231">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="281de-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="281de-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="281de-233">System.Net.Sockets</span></span>

| <span data-ttu-id="281de-234">Member</span><span class="sxs-lookup"><span data-stu-id="281de-234">Member</span></span> | <span data-ttu-id="281de-235">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="281de-236">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="281de-237">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="281de-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="281de-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="281de-239">Member</span><span class="sxs-lookup"><span data-stu-id="281de-239">Member</span></span> | <span data-ttu-id="281de-240">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="281de-241">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="281de-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="281de-242">System.Reflection</span></span>

| <span data-ttu-id="281de-243">Member</span><span class="sxs-lookup"><span data-stu-id="281de-243">Member</span></span> | <span data-ttu-id="281de-244">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-245">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-246">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-247">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="281de-248">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="281de-249">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-250">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="281de-251">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="281de-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="281de-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="281de-253">Member</span><span class="sxs-lookup"><span data-stu-id="281de-253">Member</span></span> | <span data-ttu-id="281de-254">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="281de-255">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="281de-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="281de-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="281de-257">Member</span><span class="sxs-lookup"><span data-stu-id="281de-257">Member</span></span> | <span data-ttu-id="281de-258">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="281de-259">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="281de-260">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="281de-261">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="281de-262">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="281de-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="281de-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="281de-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="281de-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="281de-267">Member</span><span class="sxs-lookup"><span data-stu-id="281de-267">Member</span></span> | <span data-ttu-id="281de-268">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="281de-269">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="281de-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="281de-270">System.Security</span></span>

| <span data-ttu-id="281de-271">Member</span><span class="sxs-lookup"><span data-stu-id="281de-271">Member</span></span> | <span data-ttu-id="281de-272">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="281de-273">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="281de-274">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-275">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="281de-276">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="281de-277">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="281de-278">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="281de-279">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="281de-280">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="281de-281">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="281de-282">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="281de-283">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="281de-284">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="281de-285">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="281de-286">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="281de-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="281de-287">System.Security.Claims</span></span>

| <span data-ttu-id="281de-288">Member</span><span class="sxs-lookup"><span data-stu-id="281de-288">Member</span></span> | <span data-ttu-id="281de-289">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-290">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-291">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="281de-292">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-293">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-294">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="281de-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="281de-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="281de-296">Member</span><span class="sxs-lookup"><span data-stu-id="281de-296">Member</span></span> | <span data-ttu-id="281de-297">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-298">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="281de-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="281de-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="281de-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="281de-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="281de-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="281de-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="281de-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="281de-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="281de-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="281de-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="281de-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="281de-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="281de-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="281de-312">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="281de-313">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-314">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-315">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-316">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-317">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="281de-318">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-319">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="281de-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-322">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-323">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="281de-324">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="281de-325">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="281de-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="281de-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="281de-327">Member</span><span class="sxs-lookup"><span data-stu-id="281de-327">Member</span></span> | <span data-ttu-id="281de-328">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="281de-329">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="281de-330">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="281de-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="281de-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="281de-332">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-332">Member</span></span> | <span data-ttu-id="281de-333">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-334">All</span><span class="sxs-lookup"><span data-stu-id="281de-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-335">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-336">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-336">All</span></span> |
| <span data-ttu-id="281de-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="281de-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="281de-338">Todos</span><span class="sxs-lookup"><span data-stu-id="281de-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="281de-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="281de-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="281de-340">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-340">Member</span></span> | <span data-ttu-id="281de-341">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-342">Todos</span><span class="sxs-lookup"><span data-stu-id="281de-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="281de-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="281de-343">System.Security.Policy</span></span>

| <span data-ttu-id="281de-344">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-344">Member</span></span> | <span data-ttu-id="281de-345">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-346">Todos</span><span class="sxs-lookup"><span data-stu-id="281de-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="281de-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="281de-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="281de-348">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-348">Member</span></span> | <span data-ttu-id="281de-349">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="281de-350">Todos</span><span class="sxs-lookup"><span data-stu-id="281de-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="281de-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="281de-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="281de-352">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-352">Member</span></span> | <span data-ttu-id="281de-353">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-354">Todos</span><span class="sxs-lookup"><span data-stu-id="281de-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="281de-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="281de-355">System.Threading</span></span>

| <span data-ttu-id="281de-356">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-356">Member</span></span> | <span data-ttu-id="281de-357">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-358">All</span><span class="sxs-lookup"><span data-stu-id="281de-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="281de-359">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="281de-360">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="281de-361">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="281de-362">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="281de-363">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="281de-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="281de-364">System.Xml</span></span>

| <span data-ttu-id="281de-365">Miembro</span><span class="sxs-lookup"><span data-stu-id="281de-365">Member</span></span> | <span data-ttu-id="281de-366">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="281de-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="281de-367">All</span><span class="sxs-lookup"><span data-stu-id="281de-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="281de-368">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="281de-369">Todas</span><span class="sxs-lookup"><span data-stu-id="281de-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="281de-370">Vea también</span><span class="sxs-lookup"><span data-stu-id="281de-370">See also</span></span>

- [<span data-ttu-id="281de-371">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="281de-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="281de-372">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="281de-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="281de-373">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="281de-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
