<!-- Possible solution 1 -->
app.use(cors({
  origin: [
    'http://localhost:5173',
    'http://test.com',
    'http://test2.com',
    'http://test3.com',
  ],
  optionSuccessStatus: 200,
  credential: true
}))


<!-- Possible solution 2 -->
const corsOptions = {
  origin: '*', // Allow requests from any origin
  methods: ['GET', 'POST', 'PUT', 'DELETE', 'PATCH', 'OPTIONS'], // Allow all HTTP methods
  allowedHeaders: ['Content-Type', 'Authorization'],
  credentials: true
};
app.use(cors(corsOptions));


<!-- Possible solution 3 -->
app.use(cors({
  'allowedHeaders': ['sessionId', 'Content-Type'],
  'exposedHeaders': ['sessionId'],
  'origin': '*',
  'methods': 'GET,HEAD,PUT,PATCH,POST,DELETE',
  'preflightContinue': false
}));

