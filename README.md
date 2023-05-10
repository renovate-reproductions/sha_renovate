# sha_renovate

Reproduction repo 

The expected result:

MR opened with the file .sha.txt
The update:
1f699d2bfc99bbbe4c1ed5bb8fc21e6911d69c6e -> 3a95ffc8257927bcdc1050733804dc7aa01dcbbc

Currently Renovate is disabled for this repo. No idea how to activate it.

In my production environment:

```shell
DEBUG: Matched 1 file(s) for manager regex: .sha.txt (repository=automotive/functional-safety/man-pages)
<--- Last few GCs --->
[15:0x6b833d0]   129843 ms: Mark-sweep 4045.1 (4133.6) -> 4041.2 (4133.6) MB, 4174.9 / 0.0 ms  (average mu = 0.420, current mu = 0.229) allocation failure; scavenge might not succeed
[15:0x6b833d0]   135245 ms: Mark-sweep 4056.9 (4133.6) -> 4052.7 (4158.9) MB, 5038.3 / 0.0 ms  (average mu = 0.264, current mu = 0.067) allocation failure; scavenge might not succeed
<--- JS stacktrace --->
FATAL ERROR: Reached heap limit Allocation failed - JavaScript heap out of memory
 1: 0xb7a940 node::Abort() [/opt/buildpack/tools/node/18.16.0/bin/node]
 2: 0xa8e823  [/opt/buildpack/tools/node/18.16.0/bin/node]
 3: 0xd5c940 v8::Utils::ReportOOMFailure(v8::internal::Isolate*, char const*, bool) [/opt/buildpack/tools/node/18.16.0/bin/node]
 4: 0xd5cce7 v8::internal::V8::FatalProcessOutOfMemory(v8::internal::Isolate*, char const*, bool) [/opt/buildpack/tools/node/18.16.0/bin/node]
 5: 0xf3a3e5  [/opt/buildpack/tools/node/18.16.0/bin/node]
 6: 0xf4c8cd v8::internal::Heap::CollectGarbage(v8::internal::AllocationSpace, v8::internal::GarbageCollectionReason, v8::GCCallbackFlags) [/opt/buildpack/tools/node/18.16.0/bin/node]
 7: 0xf26fce v8::internal::HeapAllocator::AllocateRawWithLightRetrySlowPath(int, v8::internal::AllocationType, v8::internal::AllocationOrigin, v8::internal::AllocationAlignment) [/opt/buildpack/tools/node/18.16.0/bin/node]
 8: 0xf28397 v8::internal::HeapAllocator::AllocateRawWithRetryOrFailSlowPath(int, v8::internal::AllocationType, v8::internal::AllocationOrigin, v8::internal::AllocationAlignment) [/opt/buildpack/tools/node/18.16.0/bin/node]
 9: 0xf088e0 v8::internal::Factory::AllocateRaw(int, v8::internal::AllocationType, v8::internal::AllocationAlignment) [/opt/buildpack/tools/node/18.16.0/bin/node]
10: 0xeffeac v8::internal::FactoryBase<v8::internal::Factory>::AllocateRawArray(int, v8::internal::AllocationType) [/opt/buildpack/tools/node/18.16.0/bin/node]
11: 0xf00025 v8::internal::FactoryBase<v8::internal::Factory>::NewFixedArrayWithFiller(v8::internal::Handle<v8::internal::Map>, int, v8::internal::Handle<v8::internal::Oddball>, v8::internal::AllocationType) [/opt/buildpack/tools/node/18.16.0/bin/node]
12: 0x10b0ed2  [/opt/buildpack/tools/node/18.16.0/bin/node]
13: 0x10b9b44  [/opt/buildpack/tools/node/18.16.0/bin/node]
14: 0x10e5218  [/opt/buildpack/tools/node/18.16.0/bin/node]
15: 0x114684d v8::internal::JSObject::AddDataElement(v8::internal::Handle<v8::internal::JSObject>, unsigned int, v8::internal::Handle<v8::internal::Object>, v8::internal::PropertyAttributes) [/opt/buildpack/tools/node/18.16.0/bin/node]
16: 0x11af2c3 v8::internal::Object::AddDataProperty(v8::internal::LookupIterator*, v8::internal::Handle<v8::internal::Object>, v8::internal::PropertyAttributes, v8::Maybe<v8::internal::ShouldThrow>, v8::internal::StoreOrigin, v8::internal::EnforceDefineSemantics) [/opt/buildpack/tools/node/18.16.0/bin/node]
17: 0x11b00d6 v8::internal::Object::SetProperty(v8::internal::LookupIterator*, v8::internal::Handle<v8::internal::Object>, v8::internal::StoreOrigin, v8::Maybe<v8::internal::ShouldThrow>) [/opt/buildpack/tools/node/18.16.0/bin/node]
18: 0xd76b8e v8::Object::Set(v8::Local<v8::Context>, unsigned int, v8::Local<v8::Value>) [/opt/buildpack/tools/node/18.16.0/bin/node]
19: 0x7fd2b034d[323](https://<redacted>/automotive/functional-safety/renovate-runner/-/jobs/12255890#L323) WrappedRE2::Exec(Nan::FunctionCallbackInfo<v8::Value> const&) [/opt/buildpack/tools/renovate/35.77.0/node_modules/re2/build/Release/re2.node]
20: 0x7fd2b0347[333](https://<redacted>/automotive/functional-safety/renovate-runner/-/jobs/12255890#L333)  [/opt/buildpack/tools/renovate/35.77.0/node_modules/re2/build/Release/re2.node]
21: 0x1680f2f  [/opt/buildpack/tools/node/18.16.0/bin/node]
/usr/local/bin/renovate: line 6:    15 Aborted                 (core dumped) /opt/buildpack/tools/renovate/35.77.0/bin/renovate "$@"
Uploading artifacts for failed job
```
