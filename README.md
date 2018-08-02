/*Redux*/
	*Action: Objeto que pode conter dados e informa ao reducer o que fazer.
	*Reducer: Função que retorna os dados transformados
	*State: Informação usada pelo aplicativo


	/*Função Reducer*/
	/*Toda vez que o reducer for chamada, o estado antigo é repassado ao reducer*/
	/*Sempre que mudar o estado, deve ser retornado um novo Objeto state*/
	const reducer = (state = [], action) => {
		if(action.type === 'split_string') {
			return action.payload.split('');
		} else if (action.type === 'add_character') {		
			return [...state, action.payload]; //Novo Objeto
		}
		return state;
	}

	/*Criado Store do Reducer*/
	const store = Redux.createStore(reducer);

	store.getState();

	/*Object Action*/
	const action = {
		type: 'split_string',
		payload: 'asdf'
	}

	/*Faz com que o Objeto Action seja passado pela função Reducer*/
	store.dispatch(action);

	store.getState();

	const action2 = {
		type: 'add_character',
		payload: 'a'
	}
	store.dispatch(action2)

	/*connect*/
	"connect" é uma função que retorna outra função.
	Por isso que se chama: export default connect(mapStateToProps)(Component);

/*Components*/
	->FlatList: 
		-data: Lista de dados
		-renderItem: como será mostrado cada item
		-keyExtractor: como será gerado cada key da lista