# Prefer Noun-Adjective Naming

Basically, prefer noun-adjective naming for components, and adjective-noun for props.

```txt
// Bad ❌
- CreatedStream.tsx
- CurrentUser.tsx
- EndedStream.tsx
- FullScreen.tsx
- GoLiveButton.tsx
- LiveStream.tsx
// etc...
```

```txt
// Good ✅
- CurrentUser.tsx
- FullScreen.tsx
- GoLiveButton.tsx
- StreamCreated.tsx
- StreamEnded.tsx
- StreamLive.tsx
// etc...
```

All your components are right next to each other in your directory. In addition, it’s much easier to search this way. Just type the noun Stream and choose which one you need.

[Source : Kyle Shevlin](https://kyleshevlin.com/prefer-noun-adjective-naming/)
