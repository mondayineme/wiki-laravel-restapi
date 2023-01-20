# wiki-laravel-restapi
This is a Laravel REST Api for Wiki Animals with category, this repo is very important when dealing with categories in rest api

Rewrite the Get All Animal By categories as follows so you can call it in your App

 public function getPostByCategory($id)
    {
        try {
          
            return response([
                'animals' => Animal::with('categorys')->where('category_id', $id)->orderBy('id', 'desc')->get()
             ], 200);

        } catch (\Exception $e) {
            return response()->json([
                'success' => false,
                'message' => $e->getMessage(),
            ]);
        }
    }
