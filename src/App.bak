import React from 'react'
import LoginPage from './components/pages/LoginPage'
import RegisterPage from './components/pages/RegisterPage'
import { Navigate, Route, Link, Routes } from 'react-router-dom'
import Header from './components/layouts/Header'
import Menu from './components/layouts/Menu'

type Props = {}

export default function App(props: Props) {
  return (
    <>
      <Header />
      <Menu />
      <Routes>
        <Route path="/login" element={<LoginPage />} />
        <Route path="/register" element={<RegisterPage />} />
        <Route path="/" element={<Navigate to="/login" />} />
        <Route path="*" element={<NotFoundPage />} />
      </Routes>
    </>
  )
}

const NotFoundPage = () => (
  <div>
    <h1>404 Not Found</h1>
    <Link to="/">Go Home</Link>
  </div>
)