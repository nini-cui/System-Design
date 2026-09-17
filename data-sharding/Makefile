create-migration:
	@read -p "Enter the sequence name: " SEQ; \
	migrate create -ext sql -dir ./schema/migrations -seq $${SEQ}

migrate-up:
	migrate -path=./schema/migrations -database "$(SHARD1_DATABASE_URL)" up
	migrate -path=./schema/migrations -database "$(SHARD2_DATABASE_URL)" up
	migrate -path=./schema/migrations -database "$(SHARD3_DATABASE_URL)" up

migrate-down:
	migrate -path=./schema/migrations -database "$(SHARD1_DATABASE_URL)" down 1
	migrate -path=./schema/migrations -database "$(SHARD2_DATABASE_URL)" down 1
	migrate -path=./schema/migrations -database "$(SHARD3_DATABASE_URL)" down 1