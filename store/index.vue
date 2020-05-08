//create store
export const state = () =>({
	posts: {}
});

// getters
export const getters = {
	posts(state) {
		return state.posts;
	}
};

// Mutations
export const mutations = {
	SET_POSTS(state, posts) {
		state.posts = posts;
	}
};


// actions
export const actions = {
	SET_POSTS({commit}, posts) {
		commit("SET_POSTS", posts);
	}
};

