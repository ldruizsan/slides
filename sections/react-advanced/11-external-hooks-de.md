# Externe Hooks

## Externe Hooks

Viele zusätzliche Hooks werden von der React-Community entwickelt

Einsatzgebiete z.B.:

- Abfragen von APIs
- Verwenden von globalem State
- Verwenden von _localStorage_ für den state
- Media Queries
- Abfrage der Scrollposition
- ... (siehe [awesome-react-hooks](https://github.com/rehooks/awesome-react-hooks))

## Beispiel: react-query

<https://github.com/tannerlinsley/react-query>

Viel genutzter Hook, der beim Abfragen von APIs hilfreich sein kann

## Beispiel: react-query

Einfache Verwendung:

```js
const TodoDisplay = () => {
  const [id, setId] = useState(0);
  const { status, data } = useQuery(`todo_${id}`, () =>
    fetchTodo(id)
  );
  return (
    <div>
      {status === 'success' ? data.title : status}
      <button onClick={() => setId(id + 1)}>next</button>
    </div>
  );
};

const fetchTodo = (id) =>
  fetch(
    `https://jsonplaceholder.typicode.com/${id}`
  ).then((response) => response.json());
```
