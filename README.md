npx nest generate library common
npx nest generate module database -p common
npx nest generate module config -p common
npx nest generate module logger -p common

npx nest g app reservations
npx nest g resource reservations
apps/reservations: docker build ../../ -f Dockerfile -t micro_reservations
apps/reservations: docker run micro_reservations

npx nest g app auth
npx nest g module users -p auth
npx nest g controller users -p auth
npx nest g service users -p auth