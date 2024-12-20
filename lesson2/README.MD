#### **Понимание компонентов и JSX**

##### **1. Что такое компоненты**

**Компоненты** — это основа React и React Native. Они позволяют разделить пользовательский интерфейс на независимые, многократно используемые части.

1.  **Основные принципы работы с компонентами:**
    
    -   **Повторное использование:** Один компонент можно использовать в разных местах приложения.
    -   **Изоляция:** Каждый компонент управляет своим состоянием и поведением.
2.  **Типы компонентов в React:**
    
    -   **Функциональные компоненты** (рекомендуются к использованию):
        -   Это обычные JavaScript-функции, которые возвращают JSX (структуру интерфейса).
        -   Просты в написании и поддержке.
        -   Пример:
            
            ```jsx
            const Greeting = () => {
              return <Text>Привет, React Native!</Text>;
            };
            
            ```
            
    -   **Классовые компоненты** (устаревший подход):
        -   Основаны на классах JavaScript.
        -   Имеют метод `render()`, который возвращает JSX.
        -   Используются редко, так как функциональные компоненты с хуками заменили их.
        -   Пример:
            
            ```jsx
            class Greeting extends React.Component {
              render() {
                return <Text>Привет, React Native!</Text>;
              }
            }
            
            ```
            

----------

##### **2. JSX**

**JSX** — это синтаксис, позволяющий писать XML-подобный код внутри JavaScript.

1.  **Отличия JSX от HTML:**
    
    -   В JSX используются компоненты, написанные с заглавной буквы (`<MyComponent />`), тогда как в HTML — стандартные теги (`<div>`, `<p>`).
    -   Атрибуты пишутся в стиле camelCase (например, `onPress`, а не `onpress`).
    -   Вместо `class` используется `className`.
2.  **Использование JavaScript в JSX:**
    
    -   JavaScript-код можно вставлять в JSX с помощью фигурных скобок `{}`.  
        Пример:
        
        ```jsx
        const name = "Алексей";
        return <Text>Привет, {name}!</Text>;
        
        ```
        

----------

##### **3. Props**

**Props** — это способ передачи данных в компоненты.

1.  **Что такое props:**
    
    -   Props (свойства) передаются компоненту как параметры.
    -   Компонент получает props как объект.
2.  **Пример использования props в функциональном компоненте:**
    
    ```jsx
    const Greeting = (props) => {
      return <Text>Привет, {props.name}!</Text>;
    };
    
    // Вызов компонента:
    <Greeting name="Алексей" />
    
    ```
    

----------

#### **Стилизация компонентов**

##### **1. StyleSheet**

**StyleSheet** — это встроенный метод React Native для создания стилей.

1.  **Создание стилей:**
    -   Стили создаются с помощью функции `StyleSheet.create()`.
    -   Пример:
        
        ```jsx
        import { StyleSheet, Text, View } from 'react-native';
        
        const App = () => {
          return (
            <View style={styles.container}>
              <Text style={styles.text}>Привет, React Native!</Text>
            </View>
          );
        };
        
        const styles = StyleSheet.create({
          container: {
            flex: 1,
            justifyContent: 'center',
            alignItems: 'center',
            backgroundColor: '#f0f0f0',
          },
          text: {
            color: 'blue',
            fontSize: 20,
          },
        });
        
        export default App;
        
        ```
        

----------

##### **2. Inline-стили**

**Inline-стили** — это стили, которые прописываются прямо внутри компонента.

1.  **Пример:**
    
    ```jsx
    <Text style={{ color: 'red', fontSize: 18 }}>Это красный текст</Text>
    
    ```
    
2.  **Преимущества и недостатки:**
    
    -   -   Быстрое добавление стилей.
    -   -   Сложно управлять, если стили становятся сложными.

----------

##### **3. Гибридный подход**

**Гибридный подход** сочетает использование `StyleSheet` и inline-стилей.

1.  **Пример:**
    
    ```jsx
    <Text style={[styles.text, { color: 'green' }]}>Это зеленый текст</Text>
    
    ```
    
    -   Здесь `styles.text` берется из `StyleSheet`, а `color: 'green'` добавляется поверх.
    -   Приоритет у inline-стилей, если они конфликтуют со стилями из `StyleSheet`.
