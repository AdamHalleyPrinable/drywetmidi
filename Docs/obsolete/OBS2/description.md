Now MIDI file reading uses buffering by default so `ReaderSettings.ReadFromMemory` property is deprecated. By default buffering policy is [BufferingPolicy.UseFixedSizeBuffer](xref:Melanchall.DryWetMidi.Core.BufferingPolicy.UseFixedSizeBuffer) and [BufferSize](xref:Melanchall.DryWetMidi.Core.ReaderSettings.BufferSize) is `4096` which gives the same reading speed as putting all data in memory. But if you want, you can specify `BufferingPolicy = BufferingPolicy.BufferAllData` to achieve the same behavior as with `ReadFromMemory`:

```csharp
MidiFile.Read("Great MIDI file.mid", new ReadingSettings
{
    ReaderSettings = new ReaderSettings
    {
        BufferingPolicy = BufferingPolicy.BufferAllData
    }
});
```