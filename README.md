# Flipped classroom med React Native och en gissningslek

Du ska bygga en mobilapp där användaren gissar ett hemligt tal.

En gissningslek är ett bra sätt att lära sig grunderna i React Native, inklusive komponenter, tillståndshantering och användargränssnitt.

En enkel gissningslek består av följande delar:

Ett textfält för att ange en gissning
En knapp för att skicka in gissningen
En textvisning för att ge feedback om gissningen var för hög, för låg eller korrekt

## Mål

Efter uppgiften ska du kunna:

- använda `View`, `Text`, `TextInput` och `Button` i React Native
- hantera inmatning och spellogik med `useState`
- kontrollera att användarens inmatning är giltig
- köra en Expo-app i Android-emulator eller iOS-simulator

### Läs och förklara

Börja läsa här: https://reactnative.dev/docs/getting-started
och läs fram till och med: handling text input: https://reactnative.dev/docs/handling-text-input

Läs även avsnitten om `value`, `onChangeText` och `keyboardType` i [React Natives dokumentation om TextInput](https://reactnative.dev/docs/textinput).

Några frågor att svara på innan du börjar bygga spelet:

1. Vilka komponenter motsvarar ungefär `div`, `p`, `input` och `button` från React för webben?
2. Vilken information behöver spelet lagra i state?
3. Varför behöver texten från `TextInput` omvandlas till ett tal innan du jämför den med det hemliga talet?
4. Varför behöver du validera inmatningen även om du visar ett numeriskt tangentbord?
5. Anta att det hemliga talet är 42. Vad ska appen visa efter gissningarna 20, 70 och 42?

### Skapa projektet

Skapa en ny app med en tom JavaScript-mall:

```bash
npx create-expo-app@latest GuessingGame --template blank
cd GuessingGame
npx expo start
```

`blank`-mallen ger ett enkelt projekt utan navigering. I denna uppgift arbetar du i `App.js`. Se [Expos guide till projektmallar](https://docs.expo.dev/more/create-expo/).

### Förbered din virtuella mobil

Välj spåret för din dator:

| Dator   | Verktyg        | Testmiljö        |
| ------- | -------------- | ---------------- |
| Windows | Android Studio | Android Emulator |
| Mac     | Xcode          | iOS Simulator    |

Om du har windows så ska du köra android och om du har mac så kan du köra antingen android eller ios. Gå igenom installationsguiden här: [set-up-your-environment](https://reactnative.dev/docs/set-up-your-environment)

### En början på spelet

Öppna `App.js`, ändra texten på startsidan till **Min gissningslek** och kontrollera att ändringen syns på den virtuella mobilen.

Lägg sedan till ett textfält och visa texten som användaren skriver. Du kan använda följande delar inne i din komponent, efter att ha importerat `useState`, `TextInput` och `Text`:

```jsx
const [guess, setGuess] = useState("");
```

```jsx
<TextInput
  value={guess}
  onChangeText={setGuess}
  placeholder="Skriv din gissning"
  keyboardType="numeric"
/>
<Text>Du skrev: {guess}</Text>
```

`TextInput` hanterar text. `keyboardType` påverkar tangentbordet, medan din kod behöver kontrollera innehållet.

Slutför sedan hela spelet.
