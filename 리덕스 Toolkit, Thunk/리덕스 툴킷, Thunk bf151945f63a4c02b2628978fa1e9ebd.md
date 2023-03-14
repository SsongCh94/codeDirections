# 리덕스 툴킷, Thunk

# createSlice

`/src / redux / modules / 모듈이름.js`

### initialState

![Toolkit initialState](https://user-images.githubusercontent.com/122278657/224967730-e5476bc8-0878-46f0-aee7-b83342f3c044.png)

### createSlice

![Toolkit createSlice](https://user-images.githubusercontent.com/122278657/224967913-a5bc305d-8cb1-4d31-b335-4ba8be7b4eea.png)

### export

![Toolkit export](https://user-images.githubusercontent.com/122278657/224967915-4ebf9a55-bb93-4c53-a81e-76a43a78225a.png)

## configureStore

`/src / redux / config / configStore.js`

### store

![Store](https://user-images.githubusercontent.com/122278657/224967902-78350e01-ae1f-4280-9ec0-b6b4ca08c7f9.png)

### usage

![Toolkit Usage](https://user-images.githubusercontent.com/122278657/224967922-85b51e6a-1164-471f-87a8-27df8f54493c.png)

# Thunk

### createAsyncThunk, initialState

![Toolkit createAsyncThunk](https://user-images.githubusercontent.com/122278657/224967908-3d2249b0-4da9-4aaf-b64d-b11429f69515.png)

### createSlice - extraReducers

![Toolkit Thunk createSlice](https://user-images.githubusercontent.com/122278657/224967917-9ad8a424-e5d4-4759-a104-d97c8610e949.png)

### Usage

```jsx
function App() {
  const dispatch = useDispatch();
  const { isLoading, error, todos } = useSelector((state) => {
    return state.todos;
  });

  useEffect(() => {
    dispatch(__getTodos());
  }, [dispatch]);

  if (isLoading) {
    return <div>로딩중...</div>;
  }

  if (error) {
    return <div>{error.message}</div>;
  }

  return (
    <div>
      {todos.map((todo) => {
        return <div key={todo.id}>{todo.title}</div>;
      })}
    </div>
  );
}
```
![Toolkit Thunk usage](https://user-images.githubusercontent.com/122278657/224967919-682a094f-9dec-463e-8377-ffb2290c65a4.png)
